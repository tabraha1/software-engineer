# Software Engineering A Practitioner's Approach

## The Process Framework

- Communication
- Planning
    - estimation
    - scheduling
    - risk analysis
- Modeling
    - analysis
    - design
- Construction
    - code
    - test
- Deployment
    - delivery
    - feedback

## Estimating Effort - Complexity

 **what are you most concerned about?**
 **what seems more complicated?**
 
- Obvious/simple/clear
    * Solution is evident to all
- Complicated
    * Consists of "known unknowns"
    * Range of right answers
    * Cause and effect are discoverable but not immediately apparent
    * Must asses the facts, apply good practice
- Complex
    * Represents "unknown knowns"
    * Requires creative/innovative approaches
    * Or too much complexity for us to solve it through analysis alone. Conduct spikes or POC to determine what might work

## INVEST - User Story

- independent
    * self-contained, testable separately (in storybook or with mock data)
    * features can developed and delivered separately
- negotiable
    * capture the essence of the user story by negotiating what can be dropped
- valuable
    * what value does it bring to the user/business
- estimable
    * story is descriptive, accurate, and concise
    * estimate best-case scenario, but add padding to handle anomolies
- small
    * can it be broken down without being too granular

## Additional Concerns

- Accuracy
    * is it testable (write test cases from the AC)
    * is title, description, and AC clear and precise
    * is it hiding additonal work
    * do you understand the story enough to do it yourself
- Atomic
    * is it small
    * how can we break this down further into smaller stories? Should we?
- Dependencies
    * does it require UX input
    * does it require another team's input or component they own
    * should be bring it up in the group discussion
- Testability
    * how can we test/demo this? Storybook
    * does it require technical acceptance
- Reuseability
    * should this a common component or module

## Acceptance Criteria

- What is an AC
    * helps define when a user story is done (or complete—hence, you say the story is complete)
    * at the end of the sprint, the demonstration is to show that the criteria are complete
    * acceptance criteria do not need to be an exhaustive list
    * just like the user story, the acceptance criteria can change with time, can even be refined during the sprint
- What makes good acceptance criteria?
    * clear pass/fail result (no partial results)
    * can contain both functional and nonfunctional requirements
    * clear and without ambiguity
    * should be implementation independent

## Defining Components

- Setup/Initial work
- Configuration
- Validation
- Is it reusable?
- Can we make a common modules?
- What if there’s an error?
- what sort of error will result
- What sort of error messages do you get?
- What’s the most practical, useful, usable, and satisfying solutions
- What will testing look like?
- How can we demo/test this?
- Use real service or do we have to use a mock?
- Are there any soft or hard dependencies?

## Cross-cutting concerns

1. caching
    - What:
        - a technically motivated cross-cutting concern once applications face issues in performance:
            - slow external systems, 
            - expensive and cachable calculations 
            - huge amount of data
        - aims to lower response times by storing data that is costly to retrieve in a potentially faster cache
        - typical example is to hold responses of external systems or databases in memory
    - Why:
        - before implementing caching, ask whether a cache is required or even possible
        - some data doesn't qualify for being cached, such as data that needs to be calculated on demand
        - is another solution other than caching possible?
        - should be avoided -- caching introduces duplication and the possibility of receiving outdated information
        - for example, if database operations are too slow, it is advisable to consider whether other means, such as indexing, can help
    - How:
        - The most straightforward way of caching information is in a single place in the application
      

## Code reviews

- UNDERSTANDABILITY
    * Use solution/problem domain names.
    * Use intention-revealing names.
    * Minimize the accessibility of classes and members.
    * Minimize the size of classes and methods.
    * Minimize the scope of local variables.
    * Don’t Repeat Yourself (DRY) within a single logical component (a package, module, or service).
    * Explain yourself in code.
    * Use exceptions rather than esoteric error codes and don’t return null.
 - LANGUAGE-SPECIFIC ISSUES
    * Use checked exceptions for recoverable conditions and runtime exceptions for programming errors.
    * Check parameters for validity as close to their specification or associated user input as possible.
    * Indicate which parameters can be null.
    * In public classes, use accessor methods, not public fields.
    * Refer to objects by their interfaces.
    * Use enums instead of int constants.
    * Use marker interfaces to define types.
    * Synchronize access to shared mutable data.
    * Prefer executors to tasks and threads.
    * Document thread safety.
- SECURITY
    * Input into a system should be checked for valid data size and range, and always sanitize any input that will be supplied to a data store, middleware, or third-party system.
    * Do not log highly sensitive information.
    * Purge sensitive information from exceptions (e.g., do not expose file paths, internals of the system, or configuration).
    * Consider purging highly sensitive data from memory after use.
    * Follow the principle of least privilege (e.g., run an application with the least privilege mode required for the correct functioning).
    * Document security-related information.
 - PERFORMANCE
    * Watch for inefficient algorithms (e.g., unnecessary multiple loops).
    * Avoid creating unnecessary objects.
    * Beware of the performance penalty of string concatenation.
    * Avoid excessive synchronization and keep synchonized blocks as small as practical.
    * Watch for potential deadlocks or livelocks in algorithms.
    * Ensure that thread-pool configuration and caching is configured correctly.
    
    
