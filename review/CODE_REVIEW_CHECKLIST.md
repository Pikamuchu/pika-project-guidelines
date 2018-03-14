# Code Review Checklist

## General
* Is there any merge conflict in the pull request? 
* Does the code build successfully?
* Does the code implements the feature / fixes the bug?
* Is all the code easily readable and well formatted acording to our conventions?
* Does it conform to our agreed coding rules?
* Is there any commented out code?
* Can any logging or debugging code be removed?
* Are parameters and variables checked for invalid values? Null values, Out of bound array indexes, ...
* Is there a proper error handling? 

## Documentation
* Do comments exist on public functions and describe the intent of the code?
* Is any unusual behavior, edge-case handling or workaround described?
* Is the use and function of third-party libraries documented?
* Is there any incomplete code with a ‘TODO’ mark?

## Testing
* Is the code testable?
* Do tests exist and are they comprehensive?
* Do tests actually test that the code is performing the intended functionality?
