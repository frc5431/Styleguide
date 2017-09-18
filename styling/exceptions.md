#Exceptions

Functions should validate that their arguments are correct and `throw` otherwise.

Functions should also validate that their preconditions are met, such as all of the `Motors` being initialized, robot being in a certain state, etc. If the function's preconditions are not met, `throw`

Document thrown exceptions in the documenting comment.

Never ignore errors in a `try...catch`. If the error must be ignored, print a warning to console.