### 🚀 100 Days of Code & Learning Tracker

Welcome to my personal learning journal! This repository serves as a daily tracker for my software development journey, concepts mastered, and technical breakthroughs. Every single day, I document what I've learned, track my streak, and build a referenceable base of technical knowledge.

---

## 📊 My Progress Dashboard

* **Current Streak:** 🔥 `Day 2`
* **Total Days Completed:** 🎯 `2 / 100`
* **Core Focus Areas:** All Technical Stuff

---

## 📅 Daily Log

### 🔹 [27-05-2026] — Javascript methods & Difference between I/O bound & CPU intensive tasks
- **Topic:** Learned JS bind(), call(), apply() methods
- **Body:** Today I learn javascript's bind(), call(), apply() methods, which are used to execute a function instantly & giving a this context to a function. call() & apply() are the same they execute instantly but bind() returns a copy of a function with this reference & arguments(`bind(), call(), apply() we can give this context`).
- I/O bound - this are mostly lightweight performance tasks like read a file, network call, fetch from DB, which doesnt require CPU utilization.
- CPU Intensive - this are powerful CPU dependent heavy tasks, like doing cryptography, video editing, or any other high CPU consuming tasks lies in this category.

---

### 🔹 [28-05-2026] — Some Node.js System Design Concepts
- **Topic:** System Design & Terminologies in Node.js
- **Body:** 
* `1 : Why we use Databases instead of In Memory Management ? ` We use Databases for security, data persistence across restarts, fast lookups with right indexing & etc. There are many things which are must for many concerns thats why you use databases instead of in memory management.
* `2 : What is the difference between process & thread & also why we call Node.js / js a single threaded language ? ` (`Process`) --> It is a global container assigned by Operating system, it consists memory, environment variables & resources. (`Thread`) --> Thread is an actual execution path within the process, node.js initiates 1 process but within that process it assigns exactly one single thread for the JS execution.
* `3 : What is mean by instance of an application & worker from cluster ?` (`Instance`) ==> means an single entity from a parent entity, our node.js application is independent entity. (`Cluster`) ==> is a module which is used to utilize the full capability of its system. In node.js we spawn child processes from the cluster module which are individual/separate instances of our node application, the primary process is used to fork the child processes/workers & also manages the http requests across the instances via round robin (in built algorithm), If a worker crashes primary process forks it again, so zero downtime.
* `3 : EventEmiiter vs Kafka/RabbitMQ` (`EventEmmiter`) runs within single node.js process, it uses volatile RAM (so across restarts data is lost), cannot scalable acrross different servers, used to pass data between modules within single microservice. (`Kafka & RabbitMQ`) used disk for data persistence, within multiple distributed networks (diff services), data wont lost across restarts, used to pass data between different microservices (full decoupled system / distributed systems). Event Emitter does not mean full Decoupled system, it just used to pass data between modules no true background processing, the await keyword makes it go in the eventLoop so thats how it works.
---

### 🔹 [30-05-2026] — Node.js Related Stuff
- **Topic:** Node.js Single Threaded Nature how processes Heavy CPU tasks ?
- **Body:** Node.js is very good for heavy I/O tasks, but its single threaded nature is not capable for CPU heavy tasks but that doesnt mean that you cannot perform heavy CPU tasks, there are various ways that one can use to perform heavy operations using (`WebAssembly`) - means write code in C++ / Rust / Go & compile it in webassembly, then next way is (`worker_threads`) - to spawn new threads to perform heavy tasks & another way is using (`Messaging Queues`).
---

### 🔹 [1-06-2026] — CSS Refresher
- **Topic:** CSS Flexbox, Box Sizing, & some Extra things
- **Body:**  Slowly understanding the structures of a webpages, today i have learned how to style a specific component, CSS is also not that hard, it's just making everything cool by implementing an layout.
- Flexbox is just a kinda tool to structure your webpage & rest all things are extras like, animations, styling, colors etc.
  
---

### 🔹 [4-06-2026] — EventLoop & Some In depth Knowledge of Event Loop
- **Topic:** EventLoop 
- **Body:**  EventLoop is a mechanism of javascript which handles asynchronous code & promises.
- It consists with 3 things, CallStack, Web API's(if using js in browser) / C++ API's or libuv library & Callback Queue
- What happens is every synchronus & asynchronous code starts executing inside the call stack one after another, asynchronous functions also run in callstack immediately until js found await keyword infront of an operation, when it founds the entry from the callstack vanish & goes in browser API's or if using node.js then the entry goes inside the libuv or something else, then what happens is if the async code is I/O task, setTimeout, setInterval or etc. then that goes in macro tasks queue, if something returns a promise it goes in micro tasks queues.
- micro tasks queue have highest priority, after the callstack gets fully drain then one after another the micro tasks queues code execute, after that single macro task queues task gets executed.
- (`If IO request goes inside the macro task but we wrap that request inside the async/await or within the promises then how does that works ? like it should go inside micro task but it goes in macro task queue ?`) Ok so what happens is the IO will go inside the macro task queue but when that executed & it returns a promise then it is pushed inside the micro task queues, so thats how the async/await or promises are so fast

- (`Network Request / IO req why it is slow ?`) It is slow because even if the backend server is very fast still it is a network request which will be slow, thats why we see the macro task gets done before the I/O req. but after the promise is returned then eventLoop sends the promise into the micro task queue.
- But remember the setTimeout only executes first when its time is lesser than the expected network req time, if u set 1 sec obviously network req will execute first but if u set it less like 100ms then setTimeout will execute first & also dont forget that Network / IO req goes inside the macro task queue first then the promise goes inside the micro task queue.

---

### 🔹 [5-06-2026] — Frontend event handling & Prototypes in JS
- **Topic:** Debouncing & throttle 
- **Body:** Before learning debouncing & throttle first lets understand what problem does it solves, in js there are many events which gets triggered 100's of times within few seconds, to avoid that we use debouncing & throttle, both does kind of similar job but with different approach. events which triggeres multiple times are scrolling, resizing window, typing in input etc.
- Debouncing - here what happens is we set a timer & it will resets automatically when the event get triggered, & it will run if after a specific time if events didnt gets triggered then it will run. So what happens timer will be set there, whenever the user suppose typing in input so the timer will gets resets everytime until user stops typing / triggering the event then after a delay it will run & thats how we stop multiple API req.

- Throttle - kind of similar but approach is diff, here we didnt reset the timer, what we do is after a specific timeframe we trigger the event so it can run like we didnt want when we scrolling the event gets triggered everytime, so we will set a delay of 400ms, so now after every 400ms the event will get triggered rather than after every small thing gets changed.

- This above concepts used to reduce the API/network request because some events triggers unnecessary anytime. it avoids them by triggering after a pause / after a specific timeframe.

