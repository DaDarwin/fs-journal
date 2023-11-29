# Intro to JavaScript
01. Which keywords are used to declare a variable in JavaScript?

   var let and const

02. What is the definition of a function?

    subprogram designed to perform a particular task

03. What are the `SOLID` principles?

    guidelines for easier maintainable code

04. Given this array: How could you remove the `pineapple`?

    ```js
    let fruit = ['apple', 'banana', 'pineapple', 'orange', 'strawberry']
    ```

    fruit.splice(3,1)

05. Given these two objects: How could you add each to the others friends arrays?

    ```js
    let you = {
        name: "You",
        hair: true,
        friends: []
    }
    let them = {
        name: "Them",
        hair: false,
        friends: []
    }
    ```

    you.friends += them.name 
    them.friends += you.name

06. Give an example of a JavaScript `Conditional`:

    code useful? use : sigh

07. What is the main difference between `parameters` and `arguments`?

    parameter is basically a variable and argument is the value of that variable

08. Instead of writing everything to the console, what is a better way to debug your code?

    debugger

09. What is the difference between a `primitive` value and a `reference` value?

    reference are a collection of similar values while primitive is a singular value

10. Demonstrate a loop that prints the numbers between -100 and 100?

    for(i=-100; i <= 100; i++ ){
        console.log(i)
    }
