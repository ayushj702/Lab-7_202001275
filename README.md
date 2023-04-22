# Lab-7_202001275


Equivalence Partitioning:

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Valid Input: day=1, month=1, year=1900</td>
    <td>Invalid Date</td>
  </tr>
  <tr>
    <td>Valid Input: day=31, month=12, year=2015</td>
    <td>the prev date</td>
  </tr>
  <tr>
    <td>Invalid Input: day=3, month=0, year=2012</td>
    <td>error message</td>
  </tr>
  <tr>
    <td>Invalid Input: day=0, month=2, year=2004</td>
    <td>error message</td>
  </tr>
  <tr>
    <td>Invalid Input: day=29, month=2, year=2000</td>
    <td>error message</td>
  </tr>
</table>

Boundary Value Analysis:

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Valid input: day=1, month=1, year=1900</td>
    <td>Invalid date</td>
  </tr>
  <tr>
    <td>Invalid input: day=0, month=10, year=2005</td>
    <td>error message</td>
  </tr>
  <tr>
    <td>Valid input: day=31, month=12, year=2015</td>
    <td>Previous date</td>
  </tr>
  <tr>
    <td>Invalid input: day=32, month=10, year=2005</td>
    <td>error message</td>
  </tr>
  <tr>
    <td>Invalid input: day=1, month=1, year=1900</td>
    <td>error message</td>
  </tr>
  <tr>
    <td>Valid input: day=21, month=9, year=2004</td>
    <td>Previous date</td>
  </tr>
  <tr>
    <td>Valid input: day=1, month=5, year=2004</td>
    <td>Previous date</td>
  </tr>
  <tr>
    <td>Valid input: day=9, month=6, year=2004</td>
    <td>Previous date</td>
  </tr>
</table>
</br>

### Problem 1 :

```
import org.junit.Test;
import static org.junit.Assert.*;

public class LinearSearchTest {

  @Test
  public void testExistingValue() {
    int[] arr = {1, 2, 3, 4, 5};
    int index = linearSearch(3, arr);
    assertEquals(2, index);
  }

  @Test
  public void testNonExistingValue() {
    int[] arr = {1, 2, 3, 4, 5};
    int index = linearSearch(6, arr);
    assertEquals(-1, index);
  }

  @Test
  public void testFirstElement() {
    int[] arr = {1, 2, 3, 4, 5};
    int index = linearSearch(1, arr);
    assertEquals(0, index);
  }

  @Test
  public void testLastElement() {
    int[] arr = {1, 2, 3, 4, 5};
    int index = linearSearch(5, arr);
    assertEquals(4, index);
  }

  @Test
  public void testEmptyArray() {
    int[] arr = {};
    int index = linearSearch(1, arr);
    assertEquals(-1, index);
  }

  @Test
  public void testNullArray() {
    int[] arr = null;
    int index = linearSearch(1, arr);
    assertEquals(-1, index);
  }
}
```

### Equivalence Partitioning:

<table>
  <thead>
    <tr>
      <th>Tester Action and Input Data</th>
      <th>Expected Outcome</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>v: a non-existent value and a[]: a non-empty array</td>
      <td>-1</td>
    </tr>
    <tr>
      <td>v: a non-existent value and a[]: an empty array</td>
      <td>-1</td>
    </tr>
    <tr>
      <td>v: a existent value and a[]: a non-empty array and v exists in a[]</td>
      <td>the index of v in a[]</td>
    </tr>
    <tr>
      <td>v: a existent value and a[]: an empty array</td>
      <td>-1</td>
    </tr>
    <tr>
      <td>v: a existent value and a[]: a non-empty array and v does not exists in a[]</td>
      <td>-1</td>
    </tr>
  </tbody>
</table>

### Boundary Value Analysis:

<table>
  <thead>
    <tr>
      <th>Tester Action and Input Data</th>
      <th>Expected Outcome</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>v: a non-existent value and a[]: an empty array</td>
      <td>-1</td>
    </tr>
    <tr>
      <td>v: a non-existent value and a[]: a non-empty array</td>
      <td>-1</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: an array of length 0</td>
      <td>-1</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: an array of length 0 in which v exists</td>
      <td>0</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: an array of length 0 in which v does not exists</td>
      <td>-1</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: an array of length >1 in which v exists at the beginning of the array</td>
      <td>0</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: an array of length >1 in which v exists at the middle of the array</td>
      <td>the index where v is first found</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: an array of length >1 in which v exists at the end of the array</td>
      <td>the last index where v is found</td>
    </tr>
  </tbody>
</table>
</br>

### Problem 2 :

### Equivalence Partitioning:

<table>
  <thead>
    <tr>
      <th>Tester Action and Input Data</th>
      <th>Expected Outcome</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>v: a non-existent value and a[]: a non-empty array</td>
      <td>0</td>
    </tr>
    <tr>
      <td>v: a non-existent value and a[]: an empty array</td>
      <td>0</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: an empty array</td>
      <td>0</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: a non-empty array where v exists one time</td>
      <td>1</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: a non-empty array where v exists multiple times</td>
      <td>the count of occurrences of v in a[]</td>
    </tr>
    
  </tbody>
</table>

### Boundary Value Analysis:

<table>
  <thead>
    <tr>
      <th>Tester Action and Input Data</th>
      <th>Expected Outcome</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>v: a non-existent value and a[]: an empty array</td>
      <td>0</td>
    </tr>
    <tr>
      <td>v: a non-existent value and a[]: a non-empty array</td>
      <td>0</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: an array of length 0</td>
      <td>0</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: an array of length 1 in which v exists</td>
      <td>1</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: an array of length 0 in which v does not exists</td>
      <td>0</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: an array of length > 1 where v exists at the start of the array</td>
      <td>the count of occurrences of v in a[]</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: an array of length > 1 where v exists at the end of the array</td>
      <td>the count of occurrences of v in a[]</td>
    </tr>
    <tr>
      <td>v: an existent value and a[]: an array of length > 1 where v exists at the middle of the array</td>
      <td>the count of occurrences of v in a[]</td>
    </tr>
  </tbody>
</table>
</br>

### Problem 3 :

### Equivalence Partitioning:

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>v=4, a=[2, 4, 6, 8, 10]</td>
    <td>1</td>
  </tr>
  <tr>
    <td>v=2, a=[2, 4, 6, 8, 10]</td>
    <td>0</td>
  </tr>
  <tr>
    <td>v=8, a=[2, 4, 6, 8, 10]</td>
    <td>3</td>
  </tr>
  <tr>
    <td>v=5, a=[2, 4, 6, 8, 10]</td>
    <td>-1</td>
  </tr>
  <tr>
    <td>v=9, a=[2, 4, 6, 8, 10]</td>
    <td>-1</td>
  </tr>
</table>

### Boundary Value Analysis:

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>v=2, a=[2]</td>
    <td>0</td>
  </tr>
  <tr>
    <td>v=10, a=[10]</td>
    <td>0</td>
  </tr>
  <tr>
    <td>v=6, a=[]</td>
    <td>-1</td>
  </tr>
  <tr>
    <td>v=6, a=[6, 8, 10]</td>
    <td>0 (smallest element in the array)</td>
  </tr>
  <tr>
    <td>v=6, a=[2, 4, 6]</td>
    <td>2 (largest element in the array)</td>
  </tr>
</table>
</br>

### Problem 4 | Triangle :

### Boundary Value Analysis:

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>invalid inputs: a=0, b=0, c=0</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>invalid inputs: a+b=c , a+c=b/td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>equilateral case: a=b=c==3</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Equilateral: a=b=c==100</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Isosceles: a=b≠c==5</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Isosceles: a≠b=c=5</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Isosceles: a=c≠b=5</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Scalene: a=b+c-1</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Scalene: b=a+c-1</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Scalene: c=a+b-1</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Maximum: a,b,c=Integer.MAX_VALUE</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Minimum: a,b,c=Integer.MIN_VALUE</td>
    <td>INVALID</td>
  </tr>
</table>

### Equivalence Partitioning:

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Valid input: a=1, b=1, c=1</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Valid input: a=2, b=2, c=3</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Valid input: a=4, b=2, c=5</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Invalid input: a=0, b=0, c=0</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid input: a=-1, b=3, c=9</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Valid input: a=1, b=1, c=1</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Valid input: a=5, b=5, c=6</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Valid input: a=5, b=4, c=7</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Invalid input: a=0, b=1, c=1</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid input: a=1, b=0, c=1</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid input: a=1, b=1, c=0</td>
    <td>INVALID</td>
  </tr>
</table>
</br>

### Problem 5 :

### Equivalence Partitioning:
<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Valid Inputs: s1 = "my", s2 = "myname"</td>
    <td>true</td>
  </tr>
  <tr>
    <td>Valid Inputs: s1 = "1", s2 = "123456"</td>
    <td>true</td>
  </tr>
  <tr>
    <td>Invalid Inputs: s1 = "", s2 = "hello world"</td>
    <td>false</td>
  </tr>
  <tr>
    <td>Invalid Inputs: s1 = "world", s2 = "hello world"</td>
    <td>false</td>
  </tr>
</table>

### Boundary Value Analysis:
<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>s1 = "", s2 = "1234567"</td>
    <td>False</td>
  </tr>
  <tr>
    <td>s1 = "my", s2 = "mycar"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "abc", s2 = "a"</td>
    <td>False</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = "abc"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "11111", s2 = "11111222223333344444"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "abc", s2 = "abc"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = "b"</td>
    <td>False</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = "a"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = "b"</td>
    <td>False</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = " "</td>
    <td>False</td>
  </tr>
</table>
</br>

