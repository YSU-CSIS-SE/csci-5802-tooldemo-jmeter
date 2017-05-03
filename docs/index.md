# Jmeter Test Cases

* User Cases for Jmeter
	* Used for Performance and Load Testing on:
		* Most useful for us - These we will demonstrate
			* Web - HTTP, HTTPS(Java, NodeJS, PHP, ...)
			* SOAP / REST Webservices
			* Database via JDBC
			* Java Objects
		* Least useful for us - These we will talk about
			* TCP
			* Native Commands or Shell Scripts
			* FTP
			* Mail - STMP, POP3, and IMAP
* Also provided
	* Test IDE
	* Command-line mode(headless) in any Java compatible OS
	* HTML Reporting

* Test Systems
	*https://jmeter.apache.org
	*elastic/elasticsearch
	
[17 minute long video demo on basic HTTP Request: https://www.youtube.com/watch?v=6Z9j1tM-kmY](https://www.youtube.com/watch?v=6Z9j1tM-kmY)





Jmeter is a performance testing tool that is used to analyze and measure a web application under different loads. Jmeter can measure both the static and dynamic resources of your application, can test how many users your website can handle at a time, and provides graphs to display your performance. Using two different type of testing Load (where jmeter models the expected usage by simulating multiple users across the service concurrently) and stress testing (where jmeter finds the maximum load capacity.

An example of when you may want to use Jmeter is if you were testing to see how many users at a time could be concurrently using an application that is run on a web server you own. It would also be valuable to you to know how your application works under different stress levels. To test this with Jmeter your start a thread group. Under this thread group you specify the location of your server. Then you put how many simulated users you want to test your application with. Next you wanna use Jmeter listeners to help display information such as putting your results in a graph. Once Jmeter runs its test you can see accurate information that would allow you to understand how your application runs under load and how many request per minute your application can handle without crashing or having slower performance. Knowing this could help you decide whether to make changes to your application and using certain scripts in Jmeter help you understand what is causing your application to bog down under heavier loads.

Although Jmeter is a very Robust system with entire books written on its applications. It is easy to install and it is very easy to make a simple test using its GUI for more advanced scripts there is more of a learning curve and but once you are aware on what needs tested it becomes easier to understand.


To create a simple test one is shown in the video linked but by steps in writing 


Add a Thread Group

First, add a Thread Group to Test Plan:

    Right-click on Test Plan
    Mouse over Add >
    Mouse over Threads (Users) >
    Click on Thread Group
    
    Add an HTTP Request Defaults

Add an HTTP Request Defaults

The HTTP Request Defaults Config Element is used to set default values for HTTP Requests in a test plan. This is particularly useful if we want to send multiple HTTP requests to the same server as part of a test. 

    Select Thread Group, then Right-click it
    Mouse over Add >
    Mouse over Config Element >
    Click on HTTP Request Defaults
    
In HTTP Request Defaults, under the Web Server section, fill in the Server Name or IP field with the name or IP address of the web server you want to test. Setting the server here makes it the default server for the rest of the items in a thread group.


Add an HTTP Cookie Manager

If your web server uses cookies, you can add support for cookies by adding an HTTP Cookie Manager to the Thread Group:

    Select Thread Group, then Right-click it
    Mouse over Add >
    Mouse over Config Element >
    Click on HTTP Cookie Manager

Now you will want to add an HTTP Request sampler to Thread Group, which represents a page request that each thread (user) will access:

    Select Thread Group, then Right-click it
    Mouse over Add >
    Mouse over Sampler >
    Click on HTTP Request

In HTTP Request, under the HTTP Request section, fill in the Path with the item that you want each thread (user) to request. . Note that you do not need to specify the server in this item because it was already specified in the HTTP Request Defaults item.


Add a View Results in Table Listener

In JMeter, listeners are used to output the results of a load test. There are a variety of listeners available, and the other listeners can be added by installing plugins.

    Select Thread Group, then Right-click it
    Mouse over Add >
    Mouse over Listener >
    Click on View Results in Table

Then simply run the test plan

