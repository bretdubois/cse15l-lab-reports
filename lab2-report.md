# Lab 2 Report
## Servers and Bugs

## Part I
This is a simple web server created in Java that adds a message using the given query.
![remoteaccess](https://github.com/bretdubois/cse15l-lab-reports/blob/main/images/lab2code1.png?raw=true)
1. The `handleRequest` method is called when a request is made to the server. 
2. The method uses `URI url` as the argument for the request.
3. The path `/add-message` returns a string that is extracted from the query and is concatenated to `str` with a newline.

![remoteaccess](https://github.com/bretdubois/cse15l-lab-reports/blob/main/images/lab2code2.png?raw=true)
1. The `main` method starts the server and the argument for this method is the provided port in the command line.
2. If there is no valid argument, the method returns an missing port error message.
3. When a valid port is provided, it passes this as an argument to a new instance of `Handler`.

Here is a demonstration of the StringServer in the browser:

<img width="483" alt="Screenshot 2023-02-13 at 10 58 03 PM" src="https://user-images.githubusercontent.com/122574417/218663027-91770627-71f9-4f28-810c-771b1c8ac693.png">
<img width="519" alt="Screenshot 2023-02-13 at 10 58 12 PM" src="https://user-images.githubusercontent.com/122574417/218663075-f2a164f8-6072-42bc-a0fe-3b788175cc73.png">


## Part II
One example from the lab of a method that contains a bug was `reversed`
This is an example of how we can use JUnit to test using a failure-inducing input:
~~~
  @Test
  public void testReversed2() {
    int[] input1 = { 1, 2, 3, 4, 5, 6 };
    int[] expected = { 6, 5, 4, 3, 2, 1 };
    assertArrayEquals(expected, ArrayExamples.reversed(input1));
  }
~~~
Input that does not induce a failure with the `reversed` method is when zero or one object is in the Array:
~~~
   @Test
  public void testReversed() {
    int[] input1 = { 1 };
    int[] expected = { 1 };
    assertArrayEquals(expected, ArrayExamples.reversed(input1));
  }
~~~

Provided below is a screenshot of the output when both tests are ran (note how only `testReversed` passes):
![remoteaccess](https://github.com/bretdubois/cse15l-lab-reports/blob/main/images/lab2junit.png?raw=true)


Finally, here is the code prior to the fix:
~~~
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
~~~

And this is the resolved version:
~~~
   static int[] reversedFixed(int[] arr) {
    int[] newArray = new int[arr.length];
    for (int i = 0; i < arr.length; i += 1) {
      newArray[arr.length - i - 1] = arr[i];
    }
    return newArray;
  }
~~~

In the original code, the incorrect array index was used to assign values from newArray to arr, so the original array was modified instead. In order to fix the code, the proper array index is used in assigning values to newArray, and the original array is unmodified.


## Part III
One of the tools I learned about and had never experienced before was using JUnit for testing purposes.
It allows for the creation of various test cases for certain components of the application to ensure it works as expected.
This can help catch errors early on that may result in runtime errors when given erroneous input.
