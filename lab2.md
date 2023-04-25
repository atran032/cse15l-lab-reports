# Lab Report 2

## Part 1
<img width="674" alt="image" src="https://user-images.githubusercontent.com/130080125/234159834-c34c6673-bd73-46b5-b11c-0aad01b8d978.png">
This is the code I used for creating a server which displays a list of strings. It consists of two parts. The top reads the URL and processes it to display an output. The bottom starts the server based on the Java commands in the terminal.

<img width="366" alt="image" src="https://user-images.githubusercontent.com/130080125/234160780-94960c7e-8b58-4501-95d9-77d29588413f.png">
Starting the server and accessing the homepage yields nothing at first.
<img width="365" alt="image" src="https://user-images.githubusercontent.com/130080125/234161063-0973cd7b-035d-4902-aadd-d789345bde2a.png">
When a proper path is included, a string is displayed on the server. In this case, the method handleRequest(URI url) was used to read the URL and add the query to the array. The ArrayList list field starts off empty but is added to with the parameter in the query. Lastly, the list is returned with the proper formating. In this instance, the URI at the top of the page is converted to a string, which is added to the list.
<img width="366" alt="image" src="https://user-images.githubusercontent.com/130080125/234162563-e845e1ea-a0e5-422e-a422-2da97f31ae65.png">
Adding another item to the list means that the same methods are called. First, the path is read. Then, the query is obtained and added to the list. Lastly, the whole list is returned. In this instance, an int was changed into a String. 

## Part 2
One failure inducing output involved testing the averageWithoutLowest(double[] arr) method from ArrayExamples. It involved having two of the lowest numbers and testing to see if they got removed.

    public void testAverage1() {
      double[] input = { 2, 3, 2, 1, 1, 3 };
      assertEquals(2.5, ArrayExamples.averageWithoutLowest(input), 0);
    }
    
Instead of getting 2.5, which is (2+3+2+3)/4, the code returns 2, or (2+3+2+3)/5. This only happens when there are duplicates of the lowest number. Consider this case:

    public void testAverage2() {
      double[] input = { 1, 2, 3 };
      assertEquals(2.5, ArrayExamples.averageWithoutLowest(input), 0);
    }
    
This test does return the right answer and we wouldn't be able to recognize there was a bug.

<img width="705" alt="image" src="https://user-images.githubusercontent.com/130080125/234165913-e7fe34b8-667c-4d85-a908-492894d76199.png">
Now that we've identified the symptom, we need to look for the bug.

    static double averageWithoutLowest(double[] arr) {
      if(arr.length < 2) { return 0.0; }
      double lowest = arr[0];
      for(double num: arr) {
        if(num < lowest) { lowest = num; }
      }
      double sum = 0;
      for(double num: arr) {
        if(num != lowest) { sum += num; }
      }
      return sum / (arr.length - 1);
    }
    
In this case, it's at the very end, where the sum is divided by the length of the whole array minus one. This works when there is only one of the lowest number, but fails when there are many, dividing the total by a number that's too large. 

    static double averageWithoutLowest(double[] arr) {
      if(arr.length < 2) { return 0.0; }
      double lowest = arr[0];
      for(double num: arr) {
        if(num < lowest) { lowest = num; }
      }
      double sum = 0;
      int i = 0;
      for(double num: arr) {
        if(num != lowest) { sum += num; }
        else { i++; }
      }
      return sum / (arr.length - i);
    }

The solution involves adding an index field i to count how many of the lowest number there are. Then, it is subtracted from the total length to yield the actual length. This way, the code can work whether we have 1, 2, or many more of a lowest number.

## Part 3
I learned a lot from the past 2 labs. One thing I didn't know before was how to use URLs 
