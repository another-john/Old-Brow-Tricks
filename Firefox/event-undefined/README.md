Since Firefox has a different event model, when you use some thing like

`<button onclick="javascript:myFunction()"></button>`

and

`function myFunction() {
event.preventDefault();
}`

The "event" will have an "undefined" error thrown by FF.

The faster way to solve this is to add event in the html attribute like:

`<button onclick="javascript:myFunction(event)"></button>`

and

`function myFunction(event) {
event.preventDefault();
}`


The other way is to add event listener through javascript rather than html attribute, or user jQuery's "on":

`$(element).on('click', function (event) { event.preventDefault();});`

which will make things much cleaner and easier.
