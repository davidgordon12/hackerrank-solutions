# HackerRank solutions

## Plus Minus
```
  public static void plusMinus(List<int> arr)
        {
            int pos = 0;
            int neg = 0;

            for (int i = 0; i < arr.Count; i++)
            {
                if (arr[i] > 0)
                    pos++;
                if (arr[i] < 0)
                    neg++;
            }

            Console.WriteLine((float)pos / arr.Count);
            Console.WriteLine((float)neg / arr.Count);
            Console.WriteLine((float)((arr.Count - pos) - neg) / arr.Count);
        }
```
                     
## Min Max Sum
```
  public static void miniMaxSum(List<int> arr)
    {
        // sort the list
        arr.Sort();
        
        long largest_sum = 0;
        long smallest_sum = 0;
        
        for(int i=0, j=4; i < (arr.Count - 1); i++, j--)
        {
            smallest_sum += arr[i];
            largest_sum += arr[j];            
        }
        
        Console.WriteLine($"{smallest_sum} {largest_sum}");
    }
```
                                        
## Time Conversion
```
  public static string timeConversion(string s)
    {   
        // get the hour
        int hour = Convert.ToInt32(s.Substring(0, 2));
        
        // remove the hour section
        string newTime = s.Substring(2);
        
        // check if its AM or PM
        bool morning = true;
        
        if(s[8] == 'P')
        {
            morning = false;
        }
        
        // remove AM/PM
        newTime = s.Remove(8);
        
        // if it is 12 AM, convert to 00:
        if(hour == 12 && s[8] == 'A')
        {
            return $"00{newTime.Remove(0,2)}";
        }
        
        // if it is 12 PM
        if(hour == 12 && s[8] == 'P')
        {
            return $"12{newTime.Remove(0,2)}";
        }
        
        // if it is morning, return the time, nothing else needs to be done
        if(morning == true)
        {
            return newTime;
        }
        
        // if it is afternoon, do the conversion
        else
        {
            return $"{12 + hour}{newTime.Remove(0,2)}";
        }
        
        return null;
    }
```
                                        
## Sparse Arrays
```
  public static List<int> matchingStrings(List<string> strings, List<string> queries)
    {
        List<int> results = new List<int>();
        
        for(int i=0;i<queries.Count;i++)
        {
            int count=0;
            
            for(int j=0;j<strings.Count;j++)
            {
                if(queries[i] == strings[j])
                {
                    count++;
                }
            }
            
            results.Add(count);
        }
        
        return results;
    }
```

## Lonely Integer
```
  public static int lonelyinteger(List<int> a)
    {
        int i = 0, j = 1, result = 0, count;
        
        for(i=0;i<a.Count;i++)
        {
            count = 0;
            for(j=0;j<a.Count;j++)
            {
                if(a[i] == a[j])
                {
                    count++;
                }
            }
            
            if(count != 2)
            {
                result = a[i];                    
            }
        }
        
        return result;
    }
```

## Diagonal Difference
```
  public static int diagonalDifference(List<List<int>> arr)
    {
        int prime_val = 0;
        int sec_val = 0;
        
        for(int i=0;i<arr.Count;i++)
        {
            prime_val += arr[i][i];
        }
        
        for(int i=0, j=arr.Count-1;i<arr.Count;i++,j--)
        {
            sec_val += arr[i][j];
        }
                
        return sec_val - prime_val;
    }
```
