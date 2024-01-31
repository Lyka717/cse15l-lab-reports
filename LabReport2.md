# Lab Report 2
By Angelica Cabusi (A17948600)\
CSE15L Joseph Politz


## `Chat Server`
__ChatServer Code:__\
![Image](L2_code1.png)
![Image](L2_code2.png)

__/add-message Commands:__ \
![Image](L2_1.png)
- Called methods:
    1) ```
       .getPath()
       ```
        a) This method does not take any parameters and is called upon a URI type variable (url), therefore, there are no relevant arguments. The ```url``` variable contains the string "/add-message?s=Hello&user=jpolitz". The```chatHistory``` string variable was initial ized during the server's creation.
    2) ```
       .contains()
       ```
       a) The relevant argument is "/add-message". If the path from ```.getpath``` contains the argument, then the conditional statement will pass.
       b) The method is called again later upon ```parameters[1]``` with the relevant parameter: "&user". If this is true, the 'if' conditional will pass.
    4) ```
       .getQuery()
       ```
       a) This method does not take any parameters and is called upon a URI type variable. This returns a string that will later be stored in the ```parameters``` string array variable after executing the following ```.split()``` method.
    5) ```
       .split()
       ```
       a) The relevant argument for ```.split()``` parameters is "=". This will split the called upon string into different strings separated by the "=" string. Therefore, the ```parameters``` variable will now have the array ```{"s", "Hello&user", "jpolitz"}```.
    6) ```
       .equals()
       ```
       a)The relevant argument for this method "s". This checks the called upon string(```parameters[0]```) if it is "s", and will pass if true. 
     6)```
       .indexOf()```
       a)The relevant argument for this method "&" since the string between s= and user= is "&". This changes the int variable, ```endIndex1```, to 5 since the method is called upon ```parameters[1]``` which is "Hello&user=".
    7) ```
       .substring()
       ```
       a)The relevant argument for this method is (0, ```endIndex1```). Which initializes the ```afterS``` string variable with "Hello".
    8) Once, the if conditional is passed, the ```User``` string variable will be initialized to "jpolitz".
    9) ```chatHistory``` will now contain the string value "jpolitz: Hello".
       
- Change

![Image](L2_2.png)
- The called methods are:
- Relevent arguments asdasd
- Change

