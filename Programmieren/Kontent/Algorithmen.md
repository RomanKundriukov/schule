
# Bubble Sort

```
internal class BubbleSort
{
    internal void Sort(int[] arr)
    {
        int zw = 0;

        for (int i = 0; i < arr.Length; i++)
        {
            for (int j = i; j < arr.Length; j++)
            {
                if (arr[i] > arr[j])
                {
                    zw = arr[i];
                    arr[i] = arr[j];
                    arr[j] = zw;
                }
            }
        }

        foreach (var item in arr)
        {
            Console.WriteLine(item);
        }
    }
}
```

# Insertion Sort

```
 internal class InsertionSort
 {
     internal void Sort(int[] arr)
     {
         for (int i = 1; i < arr.Length; ++i)
         {
             int key = arr[i];
             int j = i - 1;

             while(j >= 0 && arr[j] > key)
             {
                 arr[j + 1] = arr[j];
                 j = j - 1;
             }
             arr[j + 1] = key;
         }


         foreach (var item in arr)
         {
             Console.WriteLine(item);
         }
     }
 }
```

# Selection Sort

```
internal class SelectioinSort
{
    internal void Sort(int[] arr)
    {
        int zw = 0;
        int minIndex = 0;

        for (int i = 0; i < arr.Length - 1; i++)
        {
            minIndex = i;
            for (int j = i + 1; j < arr.Length; j++)
            {
                if (arr[j] < arr[minIndex])
                {
                    minIndex = j;

                }
            }

            zw = arr[i];
            arr[i] = arr[minIndex];
            arr[minIndex] = zw;
        }


        foreach (var item in arr)
        {
            Console.WriteLine(item);
        }
    }
}
```

# Stooge Sort

```
internal void Sort(int[] arr, int l, int h)
{
    if (l >= h)
        return;

    // If first element is smaller
    // than last, swap them
    if (arr[l] > arr[h])
    {
        int t = arr[l];
        arr[l] = arr[h];
        arr[h] = t;
    }

    // If there are more than 2 
    // elements in the array
    if (h - l + 1 > 2)
    {
        int t = (h - l + 1) / 3;

        // Recursively sort first 
        // 2/3 elements
        Sort(arr, l, h - t);

        // Recursively sort last
        // 2/3 elements
        Sort(arr, l + t, h);

        // Recursively sort first 
        // 2/3 elements again to 
        // confirm
        Sort(arr, l, h - t);
    }


    foreach (var item in arr)
    {
        Console.WriteLine(item);
    }
}
```

# Bogo Sort

```
    internal class StoogeSort
{
    internal void Sort(int[] arr, int l, int h)
    {
        if (l >= h)
            return;

        // If first element is smaller
        // than last, swap them
        if (arr[l] > arr[h])
        {
            int t = arr[l];
            arr[l] = arr[h];
            arr[h] = t;
        }

        // If there are more than 2 
        // elements in the array
        if (h - l + 1 > 2)
        {
            int t = (h - l + 1) / 3;

            // Recursively sort first 
            // 2/3 elements
            Sort(arr, l, h - t);

            // Recursively sort last
            // 2/3 elements
            Sort(arr, l + t, h);

            // Recursively sort first 
            // 2/3 elements again to 
            // confirm
            Sort(arr, l, h - t);
        }


        foreach (var item in arr)
        {
            Console.WriteLine(item);
        }
    }
}
```

---

# Combo Sort

```
         internal class ComboSort
 {
     internal void Sort(int[] arr)
     {
         int n = arr.Length;
         int gap = n;
         bool swapped = true;

         while (swapped || gap != 1)
         {
             gap = GetNextGap(gap);
             swapped = false;

             for (int i = 0; i < n - gap; i++)
             {
                 if (arr[i] > arr[i + gap])
                 {
                     int temp = arr[i];
                     arr[i] = arr[i + gap];
                     arr[i + gap] = temp;
                     swapped = true;
                 }
             }
         }

         foreach (var item in arr)
         {
             Console.WriteLine(item);
         }
     }

     internal int GetNextGap(int gap)
     {
         gap = (gap * 10) / 13;
         if (gap < 1)
             return 1;
         return gap;

     }
 }
```


# Bucket Sort

```
internal class BucketSort
{
    internal void Sort(float[] arr)
    {
        int n = arr.Length;

        // 1) Create n empty buckets
        List<float>[] buckets = new List<float>[n];
        for (int i = 0; i < n; i++)
        {
            buckets[i] = new List<float>();
        }

        // 2) Put array elements in different buckets
        for (int i = 0; i < n; i++)
        {
            int bi = (int)(n * arr[i]);
            buckets[bi].Add(arr[i]);
        }

        // 3) Sort individual buckets using insertion sort
        for (int i = 0; i < n; i++)
        {
            InsertionSort(buckets[i]);
        }

        // 4) Concatenate all buckets into arr[]
        int index = 0;
        for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < buckets[i].Count; j++)
            {
                arr[index++] = buckets[i][j];
            }
        }

        foreach (var item in arr)
        {
            Console.WriteLine(item);
        }
    }

    static void InsertionSort(List<float> bucket)
    {
        for (int i = 1; i < bucket.Count; ++i)
        {
            float key = bucket[i];
            int j = i - 1;
            while (j >= 0 && bucket[j] > key)
            {
                bucket[j + 1] = bucket[j];
                j--;
            }
            bucket[j + 1] = key;
        }
    }
}
```


# Merge Sort

```
internal class MergeSort
{
    internal void Sort(int[] arr, int l, int r)
    {
        if (l < r)
        {

            // Find the middle point
            int m = l + (r - l) / 2;

            // Sort first and second halves
            Sort(arr, l, m);
            Sort(arr, m + 1, r);

            // Merge the sorted halves
            Merge(arr, l, m, r);
        }

        foreach (var item in arr)
        {
            Console.WriteLine(item);
        }
    }

    internal void Merge(int[] arr, int l, int m, int r)
    {
        // Find sizes of two
        // subarrays to be merged
        int n1 = m - l + 1;
        int n2 = r - m;

        // Create temp arrays
        int[] L = new int[n1];
        int[] R = new int[n2];
        int i, j;

        // Copy data to temp arrays
        for (i = 0; i < n1; ++i)
            L[i] = arr[l + i];
        for (j = 0; j < n2; ++j)
            R[j] = arr[m + 1 + j];

        // Merge the temp arrays

        // Initial indexes of first
        // and second subarrays
        i = 0;
        j = 0;

        // Initial index of merged
        // subarray array
        int k = l;
        while (i < n1 && j < n2)
        {
            if (L[i] <= R[j])
            {
                arr[k] = L[i];
                i++;
            }
            else
            {
                arr[k] = R[j];
                j++;
            }
            k++;
        }

        // Copy remaining elements
        // of L[] if any
        while (i < n1)
        {
            arr[k] = L[i];
            i++;
            k++;
        }

        // Copy remaining elements
        // of R[] if any
        while (j < n2)
        {
            arr[k] = R[j];
            j++;
            k++;
        }
    }
}
```