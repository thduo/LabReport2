# LAB REPORT 3
# Name: Duong Ngo
# Professor: Joe Gibss Politz

# <u> Task 1:
Bug: Reversed method implementation
* A failure-inducing input:

```
 static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
* An input that doesn't induce a failure:

```
 static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - 1 - i];
    }
    return newArray;
  }

```

* The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above):
<u> The first output is: (failure)
![Image](output1.png)
<u> The second output is: (success)
![Image](output2.png)

* The bug before fixing: 
```
 static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
* The bug after fixing:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - 1 - i];
    }
    return newArray;
  }
```
The reason this code has logic error because here we create a new array which is the reversed version of the originial one. For example,
we have an integers array {1,2,3}, the output should be {3,2,1}. However, the bug appears because in the code block before fixing, it 
returned the original array which the caller will receive the original, unchanged array instead of the expected reversed array. Our purpose 
here is to return a new array with reversed order, not the original one. Therefore, instead of returning arr, I changed it to return 
newArray. 

# <u> Task 2:
I choose grep command:
<u> * 
1.The first command line option: -i is a command line that ignores all the distinctions or difference when searching for words in a specific 
text files. 
For example, when searching `grep -i "abstract" ./technical/chapter-8.txt`, it will search for the word abstract regardless of uppercase or lowercase
of the word. It will ignore case distinction to help the searching purpose faster. Additionally, this method is more effective in finding 
errors for specific files that we want to search that is grep -i "error" ./technical/logs/*.log, it will search for the word "error" in all files that end with
`.log` in the ./technical/logs directory. 
<u> * 2. The second command line option: -r is a command line that makes grep search recursively through directories. For example, 
when using grep -r "database" ./technical/, this command will find references to "database" across multiple files and directories.

