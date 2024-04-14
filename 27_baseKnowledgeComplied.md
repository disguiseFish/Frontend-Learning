Q1: What is a debounce function used for?


A: To execute a callback only after a specified time has elapsed without any further event triggers.

Q2: How does debouncing prevent multiple triggers?


A: By resetting the timer if the event is triggered again within the specified delay.

Q3: Where is debouncing particularly beneficial?


A: In scenarios like click requests to prevent sending multiple backend requests due to frequent user clicks.

Implementing a Throttle Function

Q4: What is the purpose of throttling in function execution?


A: To limit the frequency of function execution to only once within a specified time frame.

Q5: How is a throttle function effective in event handling?


A: It restricts callback execution to once per defined time unit, even if the event is triggered multiple times.

Q6: In what scenarios is throttling commonly used?


A: For scroll events to reduce the rate of event calls and improve performance.
Q1: What is the first step in implementing the apply function?
A: Check if the calling object is a function to ensure the method is applicable.

Q2: How do you handle the context object in a custom apply function?
A: If the context object doesn't exist, default it to window.

Q3: What is done after assigning the function as a property of the context object in apply?
A: Determine if any parameters have been passed and invoke the method using the context object.

Q4: What is the final step in the custom apply function after invoking the method?
A: Remove the temporarily added property and return the result of the function invocation.

Implementing the bind Function Manually

Q5: What is the initial step in manually implementing the bind function?
A: Verify if the calling object is a function to ensure compatibility with bind.

Q6: How are parameter values handled in a custom bind function?
A: Save a reference to the current function and collect all passed-in parameters after the first one.

Q7: What does the manually implemented bind function return?
A: A new function that, when called, applies the original function to the provided context.

Q8: How does the custom bind function ensure correct application of context?
A: It uses apply within the returned function to bind the function call to the specified context or the original this if used as a constructor.
Q1: What is the first step in manually implementing the call function? A: Verify if the caller is a function to ensure call is applied to a function.

Q2: What should be done if the context object passed to the call function does not exist? A: Set the context object to window if it's not provided.

Q3: How are arguments handled in the manual implementation of the call function? A: By slicing off all parameters after the first one to process the passed-in arguments.

Q4: What is done to the function before it is called within the custom call function? A: The function is attached as a property of the context object.

Q5: How is the function invoked in the custom call implementation? 
A: By using the context object to call the method and saving the result.

Q6: What step is taken after the function has been called in the custom call function? 
A: The property added to the context object for the call is removed.

Q7: What does the custom call function return? 
A: It returns the result of invoking the function with the specified context and arguments.


Q1: What is a shallow copy in JavaScript?

A: A process of copying an object's properties to another object where reference types are copied as references, leading to shared references among the copied objects. Shallow copy can be done using Object.assign() and the spread operator.

Q2: How does a deep copy differ from a shallow copy?

A: Deep copy creates new instances for reference types instead of copying references, ensuring the new object has completely separate instances.

Q3: What are some limitations of using JSON methods for deep copying?

A: Deep copying with JSON.parse(JSON.stringify(obj)) fails for properties containing functions, undefined, or Symbol types due to JSON format constraints.

Implementing Deep Copy

Q4: What is a commonly used method for deep copying objects?

A: Using JSON.parse(JSON.stringify(obj)) to serialize and deserialize objects, creating a deep copy.

Q5: Why might the JSON.stringify() method not be suitable for all deep copy needs?

A: It cannot handle functions, undefined, or Symbol types, which will be lost in the copied object.

Q6: How does lodash's _.cloneDeep function perform deep copying?

A: It provides a comprehensive solution for deep copying objects, including those with complex properties like functions and Symbols, ensuring a true deep copy.

Q7: How can you manually implement a deep copy function?

A: By recursively copying all properties of the object, checking for and correctly handling arrays, and cloning each property that is an object itself.

Q1: What is the basic concept behind recursive implementation for array flattening?


A: It involves iterating over each element, and if an element is an array, recursively flattening it.

Q2: How does reduce function iteration work for array flattening?


A: It uses the reduce method to concatenate each element or flattened array into a single array.

Q3: What is the method involving the spread operator for array flattening?


A: It uses the spread operator within a while loop to flatten each level of nested arrays.

Q4: How do split and toString methods achieve array flattening?


A: By converting the array to a comma-separated string and then splitting it back into an array.

Q5: How can ES6's flat method be used for array flattening?


A: By calling arr.flat(Infinity), which flattens the array regardless of the number of nested levels.

Q6: What is the regular expression and JSON method for array flattening?


A: It involves converting the array to a string with JSON.stringify, using regex to remove brackets, and parsing it back with JSON.parse.

Q1: What is function currying? 
A: A technique to transform a function with multiple parameters into a series of functions each with a single parameter.

Q2: What is the primary purpose of currying a function? 
A: To simplify functions with multiple parameters into simpler, single-parameter functions.

Q3: How does currying affect function execution? 
A: It breaks down complex function calls into simpler, chained single-argument calls.


Q1: What is the JavaScript Event Loop? 
A: An asynchronous programming model in JavaScript that handles events and callbacks, enablingsingle-threaded JavaScript to manage multiple tasks.

Q2: How does the browser's Event Loop work? 
A: It continuously checks a Task Queue and sequentially executes tasks from the queue.

Q3: What are the two types of tasks in JavaScript? 
A: Macro tasks and Micro tasks.

宏任务和微任务

Q4: What are Macro tasks and what do they include? 
A: Macro tasks include operations like timers and event callbacks. They are executed until completion before checking for Micro tasks.

Q5: What are Micro tasks and how are they used? 
A: Micro tasks include operations like Promise callbacks, which are executed as soon as possible after a Macro task.

Q6: How are Micro tasks and Macro tasks executed in relation to each other? 
A: Micro tasks are executed immediately after the current Macro task and before starting the next Macro task.

事件轮询的执行顺序和注意事项

Q7: What is the sequence of execution in the JavaScript Event Loop? 
A: The Event Loop executes the current Macro task's synchronous code, checks and executes Micro tasks, and then moves to the next Macro task.

Q8: What is important to consider regarding JavaScript's single-threaded event polling mechanism? 
A: Long synchronous operations in a Macro task can block other tasks, affecting application performance. It's better to use asynchronous operations for better performance and responsiveness.


Q1: How can you asynchronously load a JS script using a dynamic <script> tag? 
A: By creating a <script> tag, setting its src to the script URL, and appending it to the document.

Q2: What event handlers can be used to detect if a dynamically created script has loaded? 
A: The onload or onreadystatechange event handlers.

使用XMLHttpRequest或Fetch API异步加载脚本

Q3: How can XMLHttpRequest or Fetch API be used for asynchronous script loading? 
A: By sending a request to the script's URL and executing the response text as JavaScript code upon success.

Q4: What method is used to execute the script obtained via XMLHttpRequest or Fetch API? 
A: The script text is executed using eval() or the Function() constructor.

异步与同步加载的区别

Q5: What are the advantages of asynchronous script loading compared to synchronous loading in terms of page performance? 
A: Asynchronous loading improves page load speed and responsiveness, avoiding page stutter due to script blocking.

Q6: How does asynchronous loading affect the loading of other page resources? 
A: It allows other resources of the page to load and render faster by avoiding blocking.

Q7: What flexibility does asynchronous script loading offer in terms of script management? 
A: It allows dynamic loading and unloading of scripts as needed, improving page maintainability and expansibility.
Q1: What is the primary use of the 'for...in' loop in JavaScript?
A: It's used to iterate over the enumerable properties of an object.

Q2: What does the 'for...in' loop iterate through?
A: It iterates through each property name (or key name) of an object.

Q3: Does 'for...in' include inherited properties in iteration?
A: Yes, it iterates over both own properties and inherited properties.

Q4: Is 'for...in' suitable for iterating over arrays?
A: No, it's not recommended for arrays as it iterates over all enumerable properties.

Q5: What is the primary use of the 'for...of' loop in JavaScript?
A: It's used to iterate over the elements of an iterable object.

Q6: What types of objects can 'for...of' iterate over?
A: It can iterate over arrays, strings, Sets, Maps, and other iterable objects.

Q7: Can 'for...of' be used to iterate over regular objects?
A: No, it's not suitable for regular objects as it requires objects to implement the Iterator interface.

Q8: What is the main difference in what 'for...in' and 'for...of' iterate over?
A: 'for...in' iterates over property names, while 'for...of' iterates over element values.