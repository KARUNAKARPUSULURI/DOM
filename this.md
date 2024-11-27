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

// var name = "karunakar"
// const obj = {
//     name: "John",
//     sayHello: function() {
//         console.log(this.name)
//     }
// }
// const obj2 = {
//     name: "Bob",
//     sayHello: function() {
//         console.log(this.name)
//     }
// }
// const obj3 = {
//     name: "Bob",
//     sayHello: function() {
//         console.log(this.name)
//     }
// }
// console.log(obj.sayHello())
// console.log(obj2.sayHello())

// call(), apply(), bind()

const obj1 = {
    name:"john",
    age: 30,
    greet: function(a,b){
        console.log(a) // []
        console.log(b) // []
        console.log(a[0]) // []
        console.log(a[1]) // []
        // console.log(`Hi ${this.name}! I am ${a[0]}, I do cooking of ${a[1]} for my loving`)
    }
}
const obj2 = {name:"Bob", age: 20}

// const call = obj1.greet()
// obj1.greet.call(obj2)
// console.log(obj1.greet.call(obj2, 20, "biryani"))
console.log(obj1.greet.apply(obj2, [20, "biryani"]))

// var name = "karunakar"
// const obj = {
//     name: "John",
//     sayHello: function() {
//         console.log(this.name)
//     }
// }
// const obj2 = {
//     name: "Bob",
//     sayHello: function() {
//         console.log(this.name)
//     }
// }
// const obj3 = {
//     name: "Bob",
//     sayHello: function() {
//         console.log(this.name)
//     }
// }
// console.log(obj.sayHello())
// console.log(obj2.sayHello())





// call(), apply(), bind()

const obj1 = {
    name:"john",
    age: 30,
    greet: function(a,b){
        console.log(`Hi ${this.name}! I am ${a}, I do cooking of ${b} for my loving`)
    }
}
// greet = 
const obj2 = {name:"Bob", age: 20}
const obj3 = {name:"Vishnu", age: 20}
const obj4 = {name:"Rajya Laxmi", age: 20}
const obj5 = {name:"Keerthi", age: 20}
const obj6 = {name:"Meeraj", age: 20}

var boundfunc1 = obj1.greet.bind(obj2, 20, "biryani")
var boundfunc2 = obj1.greet.bind(obj3, 20, "biryani")
var boundfunc3 = obj1.greet.bind(obj4, 20, "biryani")
var boundfunc4 = obj1.greet.bind(obj5, 20, "biryani")
var boundfunc5 = obj1.greet.bind(obj6, 20, "biryani")


console.log(boundfunc1())
console.log(boundfunc2())
console.log(boundfunc3())
console.log(boundfunc4())
console.log(boundfunc5())

















 














 