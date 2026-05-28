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
---
