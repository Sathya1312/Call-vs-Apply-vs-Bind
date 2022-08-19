### Difference between call, apply and bind

1. Call: The call method binds the this value to the function and execute the function. It takes the this value and a list of arguments as parameters. Then it returns the value returned by the function, which is called using the call method.

Example:

let name = {
firstName: "Sathya",
lastName: "Priya",
};

let name1 = {
firstName: "Sachin",
lastName: "Tendulkar",
};

let printFullName = function (hometown, state) {
console.log(`${this.firstName} ${this.lastName} from ${hometown}, ${state}`);
};

printFullName.call(name, "Chennai", "Tamilnadu");
printFullName.call(name1, "Mumbai", "Maharastra");

In the above code, Call invokes the function and allow us to pass in arguments one by one.

2. Apply : The apply method binds the this value to the function and execute the function. It takes the this value and a single array object as parameters, and it returns the value returned by the function, which is called using the apply method.

Example:

let name = {
firstName: "Sathya",
lastName: "Priya",
};

let name1 = {
firstName: "Sachin",
lastName: "Tendulkar",
};

let printFullName = function (hometown, state) {
console.log(`${this.firstName} ${this.lastName} from ${hometown}, ${state}`);
};

printFullName.apply(name, ["Chennai", "TamilNadu"]);
printFullName.apply(name1, ["Mumbai", "Maharastra"]);

In the above code, Apply invokes the function and allows us to pass in arguments as an array.

3. Bind : The bind method binds the this value to the function and returns a new function. However, we still need to seperately invoke the returned function.

Example:

let name = {
firstName: "Sathya",
lastName: "Priya",
};

let name1 = {
firstName: "Sachin",
lastName: "Tendulkar",
};

let printFullName = function (hometown, state) {
console.log(`${this.firstName} ${this.lastName} from ${hometown}, ${state}`);
};

let printMyName = printFullName.bind(name, "Chennai", "TamilNadu");
let printName = printFullName.bind(name1, "Mumbai", "Maharastra");

console.log(printMyName);
console.log(printName);

//Both the above console returns the new function
// ƒ (hometown, state) {
// console.log(`${this.firstName} ${this.lastName} from ${hometown}, ${state}`);
// }

printMyName(); // calling a function
printName();

### When we have to use Apply/Call/Bind Method:

1.  Call and Apply are pretty interchangeable. Just decide whether its easier to send in an array or comma seperated list of arguments.

2.  Call is for comma(Seperated list) and apply is for Array.

3.  Bind is a bit different. It returns a new function whenever we want then call it seperately. Call and Apply method execute the current function immediately.
