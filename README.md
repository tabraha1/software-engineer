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
    - a technically motivated cross-cutting concern once applications face issues in performance
    - such as 
        - slow external systems, 
        - expensive and cachable calculations 
        - huge amount of data

## Industrial Extreme Programming 

- Readiness assessment
- Project community
- Project chartering
- Test-driven management
- Retrospectives
- Continuous learning
