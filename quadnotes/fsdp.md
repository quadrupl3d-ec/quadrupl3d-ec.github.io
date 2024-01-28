### Fundamental Software development practices
1. **Verbosity in variable name** - 
Less is the scope of variable, less verbose it must be. Meaning, keeping variable names short is a good practice if that variable is defined within a fucntion whose scope is less.
2. Below should be the high level overview of a javascript class:

        export var ClassName = function (var1, var2) {
         // all the variables
         // Helper functions or other functions
         // Methods and listeners
         }
        
3. Any code block should'nt have more than 4 indents.
4. An `empty line` depicts the starting of a logic block.
5. Never copy code, even if it is guaranteed to work.
6. `Never use terminal as sudo` unless required.
7. If you have multiple conditions in a `if or a for loop`, then specify each condition in new line.
8. Helper functions inside classes should start with an underscore `_`
9. Always leave a `space` after a `,` (Just a programming principle)
10. If a function is doing something, its name must be a `verb`. For example, if a function is creating a 3D geometry in space then its name must be `createGeometry()` and not just `geometry`.
11. Variable names must be easy to pronounce.
12. Any functions that are private but visible outside should start with `_` so that anyone trying to call it will know it is a private method and cannot be used from outside.
If the function is not visible outside and is only defined in the local scope then it need not have `_`.
13. Logical operations should be in one block, means, `Always leave a space after a logical block`.
14. Don't use what is not passed to a function. For example, using global variables within a fucntion without passing them to the function.
15. Each function should not be more than 30 lines, thereby decreasing the `Bug Exposure`.
16. No trailing whitespaces should be present.
17. Array variable names should end with an s to indicate that the variable is a collection.
