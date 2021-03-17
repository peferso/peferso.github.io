---
layout: single
title: "Postman automation with python"
author_profile: true
tags: [python, Postman, automation, API testing]
comments: true
classes: wide
toc: true
---
How to automate postman API requests using python

# A bit of context

Postman is a software used for API testing tasks. 
I am not an Postman expert. In my case, I had to use it to send a large number of forms in `.json` format to a remote host, in order to collect and analyze the `.json` response.
The goal was to ensure that the `.json` outputs contain specific fields, and that their value was appropriate according to corresponding the `.json` input.

The verification step is outside the scope of the present post. Here we will see how we can automate the Postman requests as well as how to collect and save locally the `.json` outputs.

# The automation

## Importing the necessary packages

First of all, let us overview the following python packages that I used for this task
```python
import requests
import json
import os
import sys
import time
```
* `requests`: we need this package to perform the API calls
* `json`: this package is necessary to manage `.json` files
* `os`: this package is necessary to discover the input `.json` forms and to save the outputs in the filesystem
* `time`: this package is not necessary, but I used it to print the elapsed time during requests

## Configuring the Postman connection parameters

To perform an API call we need 
* The destination url
* Authorization parameters

![Click on the code icon and select python](assets/posts/postman-automation-python/Postman-code-icon.PNG)

If you have performed a successful API call using Postman manually, you can easily obtain these parameters clicking on the *code* icon (see image). 
These parameters are contained in the script as follows:
```python
    url = "http://yourURL"
    headers = {
        'Authorization': 'authorization type',
        'Content-Type': 'application/json',
        'Cookie': 'JSESSIONID=sessionKey'
    }
```

## Load the json input files

I decided to store the `.json` files locally, one for each test. In order to discover the files we can use the `os` package as follows:
```python
listOfJsonInputs = os.listdir(inputsDIR)
```
With this command, we are storing in a list all the json input files. We can iterate over them with a `for` statement.
During the iteration, we import them one by one using the `json.load()` method:
```python
...
    with open(inputsDIR + '/' + listOfJsonInputs[i]) as f:
        jsonInput = json.load(f)
    # We need double quotes!
    payload = json.dumps(jsonInput)
...
```
And then storing them in the `payload` variable of type `str`, since `jsonInput` is of type `dict`
```python
In[1]: print(jsonInput.__class__)
<class 'dict'>

In[1]: print(payload.__class__)
<class 'str'>
```

## Making the API call

Now we are ready to perform the Postman `POST` request (which was the case I needed):
```python
...
    t1 = time.clock()
    response = requests.post(url, headers=headers, data=payload)
    t2 = time.clock() - t1
    print('Elapsed time:', t2, ' seconds.')
...
```

## Save the json output file

Finally, we can use the `response` object to access to the output in json format with the `response.json()` method. 
Here is the code to save the output in a .json file:
```python
...
    with open(outputsDIR + '/' + outputFile, 'w') as outfile:   
        json.dump(response.json(), outfile, indent=4, sort_keys=True)
...
```
note how here we need to use the `json.dump` method instead of `json.dumps` used before to save the json content into a string. 
Besides, the `indent` parameter adds indentation to the output file, making it easier to read for human eyes :rofl:.

# Final remarks

Let me know if this humble post was useful for you! :wink:
As I mentioned, I have not a huge experience using Postman, just for a specific type of tests that I had to repeat many times. 

I found interesting the possibility to automate these tasks, and python was a good solution for it.
Besides, I was able to automate the subsequent content analysis of the json outputs, necessary to complete the tests. 
Although this part is highly dependent on the test case considered and for that reason, I did not include it in the scope of this post. 
Perhaps will appear in a future entry!

With best regards.
Pedro.
