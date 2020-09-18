# Asynchronous in Javascript

## Intro

1. First of all , know this that javascript is **single-threaded**. that it !
2. So what is async exactly in javascript ? how can we handle the operations that can take a bit longer than the other and we want to run the rest of the codes asynchronously ?
   **The answer is we can offload them to the browser !** because the browser is able to use multiple threads . one for javascript and one for another task like the async tasks declared in javascript. so the execution is not blocked and the browser is resposnible for executing the async tasks and manage them in multiple threads.
3. How Javascript communicate with browser ? through defining call back functions and work with appropriate API like Browser API and Event Loop. **So The Real Magic Is Done By The Browser With Help Of Event Loop !**

## Event Loop

1. Take a Look at this picture:

   ![event-loop](./event-loop.png)
