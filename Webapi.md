WEB APIS:-  (browser apis) 
storages:- local storage, session storage

local Storage:- It is a web storage, valid until it is cleared or removed or logout, that means it doesnt have any expiration date
session storage:-  expiration will there when it the tab gets closed or cleared
cookies:- it has expiry date


Eventloop:- microtask queues -> settimeout, setinterval

console.log(window) => {setTimeout,setInterval}

function greet(){
console.log("hello")
}

greet()

setTimeout(greet+, 5000) :- it executes function after a certain delay(time)
setInterval(callback):- it executes function repeatedly after a centain delay





