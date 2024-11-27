"this" keyword:- 
The "this" keyword is a reference variable that is used to access the current object.

const obj = {
    name: "John",
    sayHello: function() {
        console.log(name);
    }
}

console.log(obj.sayHello())  //john

-------------------------------------------------------------
call():-
The call() method is used to call a function with a given this value and arguments provided individually.
-------------------------------------------------------------
Apply:-
The apply() method is used to call a function with a given this value and arguments provided as an array
-------------------------------------------------------------
bind:-
The bind() method creates a new bound function that has its this keyword set to the provided value,
-------------------------------------------------------------