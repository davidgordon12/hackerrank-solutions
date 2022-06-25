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
            int hr = 0;
            string sfx = "";
            hr = Convert.ToInt32(s.Substring(0, 2));
            sfx = s.Substring(8, 2);

            string hr_str = "12";

            if (hr == 12 && sfx == "AM")
                hr_str = "00";
            if (hr != 12 && sfx == "PM")
                hr_str = (hr + 12).ToString();
            if (hr < 10 && sfx == "AM")
                hr_str = $"0{hr}";
            if (hr > 10 && hr < 12 && sfx == "AM")
                hr_str = hr.ToString();

            s = s.Remove(0, 2);
            s = s.Remove(6, 2);
            return $"{hr_str}{s}";
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
