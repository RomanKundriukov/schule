
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