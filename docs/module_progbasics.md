# Programming Basics questions

## Computer science

### Data structures

#### What is the purpose of a list (array in some programming languages) data structure? Name some methods of it!
    The purpose of a list is to contain any arbitrary object. The list contains values in order, so if you want, you can rearange them as you like (with the .sort()/sorted() function) or you can delete a part from it (with the del() or remove() function) or you can add a new value in to it (with the append() or insert() function).
#### What is the difference between a list/array and a set?
    -The list can contain duplicates, but the set can't
    -The set data structure has no order in their collention.
    -The set can only contain hashable values (which is: floats, integers, tuples and strings), but the list can contain non-hashables too (list, set, dictionary)
#### What is the purpose and methods of a dictionary/map data structure?
    The dictionary is an immutable data structure, where you can add "keys" in pair with "values". You can give a key a new value, but you can't rename a key. You can't use indexes, you need to use the given key to get the value assigned to the key.

### Algorithms

#### Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.
    def fibseq(fib_nums):
        if fib_nums > 1:
            return fib(fib_nums-1) + fib(fib_nums-2)
        return fib_nums
#### How do you find a max value in a list/array if you can’t use any built-in functions?
    We need to use a for cycle and an if statement and a variable with the value 0 or less. The for cycle will iterate through the list and the if statement will check if the current value in the list is bigger than the variable and if it's true, then the variable's value will we switched with the for cycle's value.

    def max_of_array(array):
        max = 0
        for number in array:
            if(number > max):
                max = number
        return max

#### How do you find the average of values in a list/array if you can’t use any built-in functions?
    We need to use 2 variables with the value 0 and a for cycle. In the for cycle we need to add the current value of the for cycle to one of the variables and give +1 to the other variable. Outside of this for cycle, we can divide the variable with the list's values with the other variable which contains the number of numbers.

        def avarage_of_array(lst):
            array_length = 0
            array_num_sum = 0
            for number in lst:
                array_num_sum += number
                array_length += 1
            return array_num_sum / array_length

#### What do we call an *in-place* sort?
    The ".sort()" do this kind of sorting. During the sorting, the un-sorted list will be replaced with the sorted list.
#### Explain an algorithm which sorts a list!
    Bubble sorting is iterating through the list and always compares two elemnts from it, if the first is smaller, nothing changes, but if the other one is the smaller, then they switch places, and the bigger number will be next checked number again. This goes until the biggest number is at the end of the list, and the sorting ends, when we have a list with numbers sorted from the smallest to the biggest.
    First, we need a valuable, with the length of the array. Then we need 2 from cycles on in the other. The first for cycle will tell the program that how long do they need to check this array. The other for cycle will do the dirty work. We need to give it a range, and it will be the "n-i-1", because we need the length of the array at first, then we need to subtract the already checked numbers and lastly, we need to subtract 1, because we can't compare the last element to the nothing. In this for cycle, we need an if statement, with the following: if the currently checked element is bigger, than the next element, we need to switch their position in the array.
    As a last step, we need to return the sorted list.

        def bubbleSort(arr):
            n = len(arr)
            for i in range(n):
                for j in range(n-i-1):
                    if arr[j] > arr[j+1] :
                        arr[j], arr[j+1] = arr[j+1], arr[j]
            return arr

### Programming paradigms - procedural
#### What is the call stack? ***
    In short, it's the number of function calls (or simply "the stack"). Function call occur every time you call a user-made function or a build in function.
#### What is “Stack overflow”?  ***
    A programming error, also called as "memory leak". A common occurance during a wrongly wrote while loop which goes on forever.
#### What are the main parts of a function?
    The "def" which means define, this part will tell the program that we make a function. 
    The name of the function with a "()" (parentheses) at the end, so the program knows that it's the end of the function's name. 
    Under the name, you can write the statements the function should execute. 
    At the end, you can put a return statement. You can choose not to do that, but in this case, the function will return a "None".

### Programming languages - Python  
#### How do you use a dictionary in Python?
    -dictionary can be created using the dict() method:
        my_dictionary = dict({1:'rose',2:'pan'})
    -adding/updating items:
        my_dictionary['key'] = "value"
        this syntax will add the new item to the dictionary if the key does not exist already, if it does exist, it will update the value with "value"
    -removing items:
        Two ways of removing items : Whenever you remove item first you look for the key you would like to remove
        -del my_dictionary['key'] 
            it will remove the matches for "key" variable and remove all of its occurences. It will raise KeyError if the key does not exist
        -my_dictionary.pop("key", None) 
            It will do the same, but has 2 attributes. First is the key you are looking for , second one is the a value that should be returned if the key is not found.
        all the items can be deleted from a dictionary at once using clear() method on the dictionary
    -accessing elements:
        my_dictionary['key'] or my_dictionary[1] or my_dictionary.get(1) -> all will result in getting the key and value of the first element of the dictionary
    -Iteration:
        Dictionaries are muteable, so you can iterate through them. Either using a for loop, or with the keys() and items() method:
            for key in my_dictionary:
                print(key)    
        The loop will return all the keys and their values as accessing the key in a dictionary will always get the value
            my_items = my_dictionary.items()
        items() will separate the items into different brackets, so the programmer can see them more clearly.
        if we need only the keys, then we can use the following:
            keys = my_dictionary.keys()
        and if we need only the values from a dictionary, then we can use the following:
            values = my_dictionary.values()
#### What does it mean that an object is immutable in Python?
    In Python, the immutable object means that the object's internal state can't be changed. Immutable object are numbers, booleans, strings, tuples, frozen sets. (mutable objects: lists, sets, dictionaries)
#### What is conditional expression in Python?
    Conditional expressions are operators that evaluate something based on a condition being True or False.
        min = a if a < b else b
#### What are different types of arguments in Python?
    -default arguments | def greet(name,msg):
    -keyword arguments | def greet(name = "Bruce",msg = "Hello there")
    -positional arguments | def greet("Bruce", msg="HelloThere")
    -arbitrary positional arguments |
    -arbitrary keyword arguments |
#### What is variable shadowing? (context: variable scope) ***
    Variable shadowing occurs when a variable declared within a certain scope has the same name as a variable declared in an outer scope.
#### What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?
    -If you delete or drop a list value during iteration, then it will search for an index that doesn't exist anymore.
    -If you add a new value to the list during the iteration, then the new value or the last value (depending on the iteration) will not be iterated.
#### What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables? ***
    -LEGB rule is named after the first letter of the order that how python scope for names.
        Local (function) scope: This python scope contains that we defined in a funtion.
        Enclosing (or nonlocal) scope: This scope is exist when we have nested funtions (define a function inside a defined funtion) an it looks into them.
        Global (or module) scope: This scope contains all the names that are defined globaly.
        Built-in scope: Only created when you create or load a script.
    -Lifetime of variables is the time period while the variable/object has valid memory space.
#### If you need to access the iterator variable after a for loop, how would you do it in Python?
    The iterator variable only exists while the for loop exists.
#### What type of elements can a list contain in Python?
    The list can contain any arbitrary objects, which means it can contain anything from string and int to dictionary's, sets or even other lists
#### What is slice operator in Python and how to use?
    The slice operator is used to cut sequences, like string, tuples and lists. The "slice(start, stop, step)" operator can get 3 different values. First the start index, on which the slicing will start on OR if you give just this value, then the result will be the list's values to the given start index value (if you give 2, then only from 0-2 index will be seen.). The second is the stop index, the given index value will be the point out the last index, !but the given value will not be in the result!. The third value will be the "step", and the given index value will be cut out from the result. If you give the value "1" to the step, then nothing will happen, but if you give it 2, then it will skip over every 2nd index.
#### What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?
    -You can add (+) lists together, and the result will be the 2 list merged
    -You can use multiply (*) a list with the times of an integer, and the result will be the list's values.
#### What is the purpose of the in and not in membership operators in Python?
    They are used to check if an element is present in a sequence or not.
#### What does the + operator mean when used with strings in Python?
    The program will put them together into one string.
#### Explain f strings in Python?
    F-strings provide a concise, readable way to include the value of Python expressions inside strings.
#### Name 4 iterable types in Python!
    An iterable is any Python object capable of returning its members one at a time, permitting it to be iterated over in a for-loop. Python has 4 built-in iterable types: list, dict, tuple and set.
#### What is the difference between list/set/dictionary comprehension and a generator expression in Python?

#### Does the order of the function definitions matter in Python? Why?
    Order of the functions does not matter because you are just adding 2 new functions for example. But to actually access it you will need to write a look-up. YOu will need to call the function. And in order to have the right order you will need to call them in the main for example in the right order.
#### What does unpacking mean in Python?
    Unpacking in Python refers to an operation that consists of assigning an iterable of values to a tuple (or list) of variables in a single assignment statement. As a complement, the term packing can be used when we collect several values in a single variable using the iterable unpacking operator, *.
#### What happens when you try to assign the result of a function which has no return statement to a variable in Python?
    ValueError will raise as if you dont return a variable  from a function then you cant access it outside of the function scope.

## Software engineering

### Debugging

#### What techniques can you use while debugging a program in Python?
    -Printing: You can print out parts from the program, and you can check parts before the error or other problems
    -Debugging tool in VS Code: A very useful tool, VS Code shows you the program's running step-by-step, you can see all the valuables on the side listed, and the changes after every steps.
#### What does step over, step into and step out mean while using the debugger?
    -Step in: mIf there is a function call, it goes inside the function and you can see how the function is executing line by line till it returns and you go back to the next line right after the function call.
    -Step over: If there is a function call, it just executes it like a black box and returns the result, but you cannot see how the function was executed.
    -Step out: If you have Stepped in a function and now you want to skip seeing how the rest of the function is going to execute, you Step out and the function returns. Then, you go back to the next line, that is the line right after the function call.
#### How can you start to debug a program from a certain line using the debugger?
    You need to click beside the row number, to put a red dot beside it, then you need to run the debugger, and it will run from that point.

### Version control

#### What are the advantages of using a version control system?
    Version control systems allow you to compare files, identify differences, and merge the changes if needed prior to committing any code. 
    Versioning is also a great way to keep track of application builds by being able to identify which version is currently in development, QA, and production.
    Version control systems are useful when working in a team. Whenever someone makes changes you can compare, and new developers can catch up and see the commit history.
#### What is the difference between the working directory, the staging area and the repository in git?
    Working directory is your computer where you work at. Your changes are only yours no one can see it.
    Staging area is the area where you add the code you been working on, its the area where the code is kept if the repository, which is the "cloud" on github, has changes aswell. In this case the code is kept in staging area until you pull the changes and accept them.
#### What are remote repositories in git?
    A remote repository in Git, also called a remote, is a Git repository that's hosted on the Internet or another network.
#### Why does a merge conflict occur?
    A merge conflict is an event that occurs when Git is unable to automatically resolve differences in code between two commits.
#### Through what series of commands could you put a new file into a remote repository connected to your existing local repository?
    -git status | to check for modifications to make sure
    -git add -A | where -A means all mods
    -git commit -m | where -m means a message which should describe the changes
    -git push | to push all changes to development branch
#### What does it mean atomic commits and descriptive commit messages?
    Atomic commit means you make a commit every time you make changes or finish a feature, making commit after 2 feature chagne doesnt not go as an atomic commit. 
    Descriptive commit messages mean when you give a commit message you describe shotrly but meaningfully the changes and modifications you made on the feature/programme.
#### What’s the difference between git and GitHub?
    Git is a version control system that lets you manage and keep track of your source code history. GitHub is a cloud-based hosting service that lets you manage Git repositories.

## Software design

### Clean code

#### What does clean code mean?
    Clean code means simply, that the program code is kept clear and understandable to others. There is no variables with the name x and used in 10 different functions and you don't use the same method 10 times after each other.
#### What steps do we usually do during a clean code refactoring?
    1. You finish the code, making sure the software functions as per requested.
    2. You run through the code and do small changes. Understanding your code better, changing few things. Removing all duplications/dead code.
    3. Go through the code and :
        - moving features between objects in order to better distribute functionality among classes/functions.Meaning to move functionality to solo class/functions
        - simplifying conditional expressions, variable names for easier understanding.

### Error handling

#### What is exception handling?
    Exceptions are used in situations (with the "try" of course), where the programs can run into an error (like IndexError or ValueError), but this exception will prevent the error's occurance in the program, and execute other parts in this case (or just skips over the error, it depends on the usage)
#### What are the basics of exception handling in Python?
    ZeroDivisionError: Occurs when a number is divided by zero.
    NameError: It occurs when a name is not found. It may be local or global.
    IndentationError: If incorrect indentation is given.
    IOError: It occurs when Input Output operation fails.
    EOFError: It occurs when the end of the file is reached, and yet operations are being performed.
#### In which case should we catch an exception? Why?
    If the Python program contains suspicious code that may throw the exception, we must place that code in the try block. 
    The try block must be followed with the except statement, which contains a block of code that will be executed if there is some exception in the try block.
#### What can/should we do with an exception in the ‘except’ block?
    We can use the exception variable with the except statement. It can be executed by using the error codes as keyword (like ValueError or IndexError).
#### What does the else and finally statement do in a try-except block in Python?
    -We can also use the else statement with the try-except statement in which, we can place the code which will be executed in the scenario if no exception occurs in the try block.
    -Python provides the optional finally statement, which is used with the try statement. It is executed no matter what exception occurs and used to release the external resource. 
    The finally block provides a guarantee of the execution. We can use the finally block with the try block in which we can pace the necessary code, 
    which must be executed before the try statement throws an exception.

## Software Development Methodologies

#### What is the main goal of a retrospective meeting?
    Gather data and insights from the project and improve the weaker parts.
    Discuss the data and insights and make action items around them.
    Make a plan for improvements on the next sprint.

## Programming environment

### Unix

#### What is UNIX and what is Linux?
    Linux is an operating system built by Linus Torvalds at the University of Helsinki in 1991. 
    The UNIX OS was born in the late 1960s. AT&T Bell Labs released an operating system called Unix written in C, which allows quicker modification, acceptance, and portability.
#### What do we call the shell in Linux?
    Bash (Bourne Again Shell). A replacement from the GNU project's Bourne Shell.
#### What does root means in a Linux environment?
    root is the superuser of the Linux enviroment. This account or user name can access all files on the OS.
#### How do you access your personal files in Linux?
    The personal files are stored in the (root)/users/USERNAME folder.
#### How can you install an application in Linux?
    sudo apt install app_name
#### What is package management in Linux, what are repositories?
    Package management is a method of installing, updating, removing, and keeping track of software updates from specific repositories.
    A software repository, or “repo” for short, is a storage location for software packages.
#### How do you navigate in the filesystem with the command line?
    use cd command to navigate between folders , and ls to list the content of the folder you are located in
#### What does the following commands do: mkdir, rm, cat, cp, touch?
    -mkdir: create a directory
    -rm: removes a file or directory. 
    -cat: shows you the content of the give file/files or you can create a file with it. 
    -cp: copy a file or directory. 
    -touch: changes a file's timestamps or creates files.
#### How can you look up what does a command do in Linux if you have no internet connection?
    type -help in bash to list all available basic commads
    sudo -h for apps to list applications related commands
#### What does the following commands do: head, tail, more, less?
    head : head command is used to view the first lines of any text file
    tail: the tail command will display the last ten lines of a text file
    more: more command is used to view the text files in the command prompt
    less: it is command line utility that displays the contents of a file or a command output, one page at a time
#### How do you download a file from internet using the terminal?
    wget [URL]
