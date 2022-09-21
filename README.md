# 08.09-DZ

using System;
using System.Security.Cryptography;


string probel(string s)
{
    int l = s.Length;
    for (int i=0; i<l; i++)
    {
        if (s[i] == ' ')
        {
            l--;
            s = s.Remove(i, 1);
        }
    }
    return s;
}
string sort(string s)
{
    char[] charArray = s.ToCharArray();
    Array.Sort(charArray);
    String sort = new String(charArray);
    return sort;
}

string s1 = probel(Console.ReadLine());
string s2 = probel(Console.ReadLine());
s1= sort(s1.ToLower());
s2= sort(s2.ToLower());
int l1 = s1.Length;
int l2 = s2.Length;
if (l1 == l2)
{
    bool result = s1.Equals(s2, StringComparison.OrdinalIgnoreCase);
    if (result)
    {
        Console.WriteLine("Yes");
    }
    else
    {
        Console.WriteLine("No");
    }
}
else
{
    Console.WriteLine("No");
}


int[] array = new int[10] { 2, 3, 6, 1, 11, 7, 8, 9, 10, 12 };
Array.Sort(array);
int min = array[0], max = 0, r = 1, r1=0, max_m=0, min_m=0;
for (int i = 1; i < 10; i++)
{
    if ((array[i-1] + 1 < array[i])||(i==9))
    {
        max = array[i];
        if (r > r1)
        {
            r1 = r;
            min_m = min;
            max_m = max;
        }
        r = 1;
        min = array[i];
    }
    if (array[i-1] + 1 == array[i])
    {
        r++;
    }
}
Console.WriteLine(min_m + " " + max_m);
