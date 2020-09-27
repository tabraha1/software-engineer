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

## General Principles

- The reason it all exists
- Keep it simple, stupid!
- Maintain the vision
- What you produce, other will consume
- Be open to the future
- Plan ahead for reuse
- Think!

## Personal Software Process

- Planning
- High-level design
- High-level design review
- Development
- Postmortem

## Agility Principles

- Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.
- Welcome changing requirements, even late in development. Agile processes harness change for the customer's competitive advantage.
- Deliver working software frequently, from a couple of weeks to a couple of months, with a preference to the shorter timescale.
- Business people and developers must work together daily throughout the project.
- Build projects around motivated individuals. Give them the environment and support they need, and trust them to get the job done.
- The most efficient and effective method of conveying information to and within a development team is face-to-face conversation.
- Working software is the primary measure of progress.
- Agile processes promote sustainable development. The sponsors, developers, and users should be able to maintain a constant pace indefinitely.
- Continuous attention to technical excellence and good design enhances agility.
- Simplicity--the art of maximizing the amount of work not done--is essential.
- The best architectures, requirements, and designs emerge from self-organizing teams.
- At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behavior accordingly.

## Industrial Extreme Programming 

- Readiness assessment
- Project community
- Project chartering
- Test-driven management
- Retrospectives
- Continuous learning
