# Lab-7_202001275

Test Cases for Equivalence Partitioning:

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

Test Cases for Boundary Value Analysis:

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
