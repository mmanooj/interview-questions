# interview-questions
Interview questions for hiring engineers

## Problem solving
### FizzBuzz - (20 mins)
  For range of numbers 1 - 100, print
  1. 'Fizz' when multiple of 3
  2. 'Buzz' when multiple of 5
  3. 'FizzBuzz' when multiple of 3 & 5
  4. Number itself if none of the above
  Enhancements:
  1. Print 'Foo' when multiple of 7, 'Bar' when multiple of 11
  2. Print 'FooBar' when multiple of 7 & 11

### Given a string, find all the non-repeating permutations of the string.
For example: abc → {bca, acb, abc, cba, bac, cab}

### Smallest positive missing number in an unsorted array
{2, 3, 7, 6, 8, -1, -10, 15} => 1
{2, 3, -7, 6, 8, 1, -10, 15 } => 4
{1, 1, 0, -1, -2} => 2

### Given arrival and departure time of trains/buses, find least number of platforms to accommodate
trains/buses without keeping them in waiting state.
Case 1:
Arr[] = {9:00, 9:40, 9:50, 11:00, 15:00, 18:00}
dep[] = {9:10, 12:00, 11:20, 11:30, 19:00, 20:00}
Result: 3,
Case 2:
Arr[]={9:00, 9:40}
dep[] = {9:10, 12:00}
Result: 1

### Write a function to check if input two dimensional array is a magic square or not.
2 7 6
9 5 1
4 3 8

### Given array of numbers, find if sum of any two numbers is equal to K.

## Javascript
### Hoisting
  https://www.interviewbit.com/javascript-interview-questions/#explain-hoisting
### What is the o/p of the following: 
  var variable = 10; (()=>{ console.log(variable); var variable = 20; console.log(variable); })();
### Write a function createBase to achieve the following: 
  const addSix = createBase(6); addSix(10); // returns 16 addSix(21); // returns 27
### Write a function counter to achieve the following:
const c = counter(); c.add(5); c.add(9);
c.retrieve(); → The counter is currently at: 14
### What is the output of the following code? How would you fix this? 
  const arr = [10, 12, 15, 21]; for (var i = 0; i < arr.length; i++) { setTimeout(function() { console.log('Index: ' + i + ', element: ' + arr[i]); }, 3000);
  }

## NodeJS
### Write code to execute an array of promises sequentially without using async/await:
  a. return an array of results.
  b. error even if one of the promise fails
### Write a function retryFn that does the following
  a. Max retries = 5
  b. Retry function input: operation (synchronous function)
  c. Retry function output: a Promise resolved with the output of the operation
### Write a function delay that returns a promisfied setTimeout function
### Explain event loop architecture
### Singleton in nodejs
  (() => {
  console.log("this is the start");
  setTimeout(() => {
  console.log("Callback 1: this is a msg from call back");
  }); // has a default time value of 0
  console.log("this is just a message");
  setTimeout(() => {
  console.log("Callback 2: this is a msg from call back");
  }, 0);
  process.nextTick(() => {
  console.log("NextTick 1: this is a msg from a tick");
  })
  Promise.resolve(null).then(() => {
  console.log("Promise 1: this is a msg from promise")
  })
  console.log("this is the end");
  })();

## Design
### Service to upload csv records to 3rd party API using a NodeJS service - focus on scalability, throughput, correctness, reliability
### Given stock prices for the entire year(timestamp, stock_symbol, price), design two APIs:
  a. example: (1, DZN, 120.5), (4, DZN, 123.25), (5, DZN, 122.95), (11, DZN, 120.5),
  each price movement is a tuple (timestamp, stock_symbol, price),
  b. design API/Query for:
    i. get most recent price of the stock (in the above example, ans: 120.5)
    ii. get price of stock at a specific time, get_at(4)=123.25, get_at(6)=122.95
  c. Focus on: DB indexes(stock_symbol, date_time), caching layer, load balancer,
### HTTP caching headers, Handling db bottleneck, cache layer bottleneck
### Design API’s for the following use-cases from an employee directory system
  a. Fetch first 50 employee’s by joining date between two given dates
  b. Fetch filtered list of all employee’s whose email domain is “@abc.com"
  c. Create a new employee
  d. Update an employee Name by using his employee id
  e. Delete an employee
### Model a multistep workflow using Java classes.
  a. A step may be configured to execute either all(AND) or one(OR) of the preceding steps.
  b. generate stats for jobs in various steps, jobs succeeded/failed, latency/throughput of jobs.
  c. How to deal with transient and permanent failure in steps.
### Design builder pattern with immutable object.
  Usage pattern:
  const order = OrderBuilder.createOrder().addQuantity(10).addDescription("Test
  order").addDeliveryDate("31-06-2078").build();
  order.quantity = 30; //error
### Parking lot design
### Design an ID generator, Requirements,
  i. Should be unique & sortable( by date)
  ii. Should be 72-bit
  iii. Should be able to generate 10K ID/second
  b. Artifacts ii. A HLD of the ID generator system LLD of the ID generator logic
