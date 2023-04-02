<!-- # eventloop-assignment -->
# 1: What is the Event loop ?
Event loop in NodeJS is a mechanism through which NodeJS is able to run asynchronous code by making use of a Call stack. 

During this Event loop process, the 'calls waiting for execution' in the callback queue can be put on the call stack. 

# 2: Explain the 6 phases of the event loop
The Event Loop consists of the six phases listed below, which are repeated as long as the application's code has to be executed: 

1)Timers:
 Node.js provides timers, or functions that perform callbacks after a given amount of time.At the start of this phase. The timers are then checked in a queue or pool. All timers that are currently set are in this queue. The Event Loop compares the timer with the least wait time to the current time of the Event Loop. The timer's callback is scheduled to be triggered once the call stack is empty if the wait time has expired.

2)I/O Callbacks: 
When your program is waiting for a file to be read, it is not required to wait until the system returns with the file's content. It can keep running code and asynchronously receive the file's content when it's ready. 

Non-blocking, I/O interfaces enable us to do this. The asynchronous I/O request is queued, and the main call stack can then continue to function normally. The I/O callbacks of completed or errored out I/O operations are processed in the second phase of the Event Loop. 

3)Idle, Prepare: 
The Event Loop executes internal activities on any callbacks during this phase. Technically, there is no way to change the length or nature of this phase. During this phase, there is no mechanism in place to guarantee code execution. It is mostly used for gathering data and preparing what actions should be taken on the next tick of the Event Loop. 

4)I/O Polling: 
The Event Loop manages the I/O workload during this phase, calling the functions in the queue until the queue is empty, and calculates how long it should wait before going on to the next phase. In this phase, all callbacks are synchronously called in the order in which they were added to the queue, from oldest to newest. 

If any setImmediate() timers are scheduled during the current tick, Node.js will skip this phase and proceed to the setImmediate() phase.

5)Check:
The callbacks scheduled by setImmediate() are handled in this phase, and they will be executed once the Poll phase is idle. 

SetImmediate() in Node.js is a specific timer that executes callbacks during this period. When the poll phase is idle, this phase starts. SetImmediate() will always be executed before other timers if it is scheduled within the I/O cycle, regardless of how many timers are present. 

6)Close events:
If a socket or handle is abruptly closed, the 'close' event is emitted, this phase handles callbacks. 

All closing event callbacks are executed in this phase. A closing event of a web socket callback, for example, or process.exit() is called. This is the point at which the Event Loop has completed one cycle and is ready to go on to the next. It is primarily used to clear the application's state. 
# 3: List some best practices in server-side code development
1)IT IS BETTER TO USE ASYNC/AWAIT INSTEAD OF PROMISES THAT WILL LEAD TO CALLBACK HELL.
2)KEEP YOUR CODE SMALL TO FACILITATE READABILITY AND SCALABILITY.
3)INSTALL EXTENSIONS LIKE prettier TO FORMAT YOUR WORK.
4)Handle Errors
5)Structure your solution by components.
6)Separate Express 'app' and 'server'
7)Use only the built-in Error object.
8)Distinguish operational vs programmer errors.
9)Handle errors centrally, not within a middleware.
10)Name your functions WITH DESCRIPTIVE NAMES AND Avoid anonymous functions

# 4: What is NPM5: How do you initialize a package in npm

npm stands for Node Package Manager. It's a library and registry for JavaScript software packages. npm also has command-line tools to help you install the different packages and manage their dependencies. npm is free and relied on by over 11 million developers worldwide.

You initialize a package in npm with "npm init"

# 6: How do you run a script in the package.json ?
To execute your Script, use 
'npm run<NAME-OF-YOUR-SCRIPT>' 

# 7: Initialize a package of your choice, give it a name and install the following npm packages to it, express, mongoose, joi.

I used the follow command for the installation => npm i express mongoose joi
(you can see the packages at the root of my directory)

