# Lab Report 2

## Part 1
<img width="674" alt="image" src="https://user-images.githubusercontent.com/130080125/234159834-c34c6673-bd73-46b5-b11c-0aad01b8d978.png">
This is the code I used for creating a server which displays a list of strings. It consists of two parts. The top reads the URL and processes it to display an output. The bottom starts the server based on the Java commands in the terminal.

<img width="366" alt="image" src="https://user-images.githubusercontent.com/130080125/234160780-94960c7e-8b58-4501-95d9-77d29588413f.png">
Starting the server and accessing the homepage yields nothing at first.

<img width="365" alt="image" src="https://user-images.githubusercontent.com/130080125/234161063-0973cd7b-035d-4902-aadd-d789345bde2a.png">
When a proper path is included, a string is displayed on the server. In this case, the method handleRequest(URI url) was used to read the URL and add the query to the array. The ArrayList list field starts off empty but is added to with the parameter in the query. Lastly, the list is returned with the proper formating. In this instance, the URI at the top of the page is converted to a string, which is added to the list.

<img width="366" alt="image" src="https://user-images.githubusercontent.com/130080125/234162563-e845e1ea-a0e5-422e-a422-2da97f31ae65.png">
Adding another item to the list means that the same methods are called. First, the path is read. Then, the query is obtained and added to the list. Lastly, the whole list is returned. In this instance, an *int* was changed into a *String.* 
