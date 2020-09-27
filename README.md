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

 *what are you most concerned about?*
 *what seems more complicated?*
 
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
    - is it testable (write test cases from the AC)
    - is title, description, and AC clear and precise
    - is it hiding additonal work
    -    *Are we accounting for that work?*
    - do you understand the story enough to do it yourself
- Atomic
    - *What’s the simplest portion we can start on?*
    - how can we break this down further into smaller stories? Should we?
    - *Do we still feel like that’s two points worth of work? Or do we feel that this changes things at all?*
- Dependencies
    - does it require UX input
    - does it require another team's input or component they own
    - should be bring it up in the group discussion
- Testability
    - how can we test/demo this? Storybook
    - can the BA test this? does it require technical acceptance
- Additions
    - is there tech debt we need to refine?
    - well are there any known bugs

## Acceptance Criteria

- What is an AC
    * helps define user story as complete
    * at the end of the sprint, the demonstration is to show that the criteria are complete
    * acceptance criteria do not need to be an exhaustive list
    * just like the user story, the acceptance criteria can change with time, can even be refined during the sprint
- What makes good AC?
    * clear pass/fail result (no partial results)
    * can contain both functional and nonfunctional requirements
    * clear and without ambiguity
    * should be implementation independent
    
 - Top Mistakes:
    * Too formal or too much detail: 
        * good information is not lost, but it does not complicate the user story 
        * detailed story during the sprint planning, might see all the details are present and may skip the detailed conversation
        * communication is the central point of the user story, so do not do anything that will limit or restrict it
    * Technical tasks masquerading as stories: 
        * if some stories are just technical tasks, you may not end up with working code at the end of the sprint. 
        * this may be fixed by making it a spike
    * Skipping the conversation: 
        * if you skip the ac conversation, you move in  wrong direction, miss boundary cases, overlook customer needs

## Grooming backlog

   - making sure that high priority items are floated to the top and not getting buried
   - important as you and your team approach the start of a new sprint
   
   - newly added issues go to the bottom by default
   - To prioritize issues in your backlog, you simply move the high priority issues up and move the low priority issues down
   - right-click the issue you want to move and select the Top of Backlog option
   - hold down the Shift or Ctrl key on your keyboard for multiple issues
   
   - flag issues that are important or require special attention, which is done by right-clicking an issue and selecting the Add flag option
   - display the labels that have been added to issues such as technical acceptance or tech debt
   - create custom hyperlinks for issues or UX specs
   - issue A might be blocking issue B, or issue C might be a duplicate of issue D
   - add descriptions to the issue to convey this information, or delete one of the issues in the case of duplication
   - When an issue is being cloned, a Clone link is automatically created between the two issues, establishing a relationship

## Defining Components

- UI
  - User navigation (forward/backward)
    * *How does the user know the task was complete*
    * any validation error/confirmation
  - *Do need to make a common component for that?*
  - *Does it need to configurable for certain things?*
    * *Are we accounting for that work?*
    * *It’ll be more complicated if we make it configurable. Do we need to necessarily do that right now?*
  - *Any work around validation?*
    * *Is it complicated? Are we saying the only validation is checkbox is set up?*
  - *Do we need to integrate this into another component?*
    * *can it be worked indepedently in storybook or mock data*
  - *Do we need create an endpoint for this?*
- API
    - *How much is work going to go into creating this endpoint?*
        * *Are there certain fields we need to set?*
        * *What type of event will be published*
   - *Do we need to update the schema*
        
## Breaking down epics into good user stories

- Try to create user stories which are simple and will translate gracefully into views (the V in MVC)
- With less technical words, focus on what the users will see as a result of their actions, then create a user story for each of those results, if they solve a problem
- don't worry about actions that can result in a problem or nothing
    * if the user searches for a car in our grocery surplus webshop, that's their problem for now
    * later on, we might want to help them, by suggesting something they can actually buy here
- easier to have a great and actionable discussion on small and simple user stories than epics

## Cross-cutting concerns

There are two main types of concerns in a software system (they can intersect too):
  - Core concern: 
    * functionality fundamental to the system 
        * ex. the logic related to the calculation of employee salaries is core concerns of a HR system
    * The logic for each core concern is typically localized to particular components.
  - Cross-cutting concern: 
    * functionality that is used in multiple areas, possibly spanning multiple layers of the application
    * security, logging, caching, and error handling

1. Synchronous request
    - when a client makes a synchronous request, it waits for a response
    - a request-reply pattern is used to handle synchronous requests
2. Asynchronous request (message queue)
    - to process requests asynchronously, the publish-subscribe pattern can be used
3. Exception management
    - can be handled in a centralized and consistent way
    - common boilerplate code to perform operations - logging of exceptions and communicating an exception occurred back to user
    - Failures in the application should not leave it in an unstable state or corrupt data
    - should be logged as the information may be helpful in resolving an issue
    - sensitive information should not be revealed
4. Logging
    - Date/time: imperative to know when the event took place
    - Source: the source/location of the event
    - Log Level/Severity: the level/severity of the log entry
    - Message: description or detail explaining the log entry
5. Auditing
    - cross-cutting concern of many software applications is the auditing of data changing operations
    - ex. date/time that it occurred and the identity of the individual who made the change
    - may have requirement to record information about nature of data change, such as the old and new values
    - in event-driven systems, persisting events and their details can serve as the audit trail
4. caching
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
 5. Auditing
    - cross-cutting concern of many software applications is the auditing of data changing operations
    - ex. date/time that it occurred and the identity of the individual who made the change
    - may have requirement to record information about nature of data change, such as the old and new values
    - in event-driven systems, persisting events and their details can serve as the audit trail
      
## Database Migrations

- Any and all changes to a database schema must be codified in a series of “database migration” scripts. Migration files should be named and ordered by date.  
- Database migrations should support both schema changes, as well as sample data insertion.
- Running database migrations should be part of the project launch (via Make start, see below.) and must be enforced
- Running database migrations must be automated and should be part for any build (integration, feature branch builds for PR etc.)
- It should be possible to indicate which migrations run on which environments (or skip which ones) so that migrations that deal with sample data creation can be skipped in production, for example.
- These rules apply to all data storage systems: relational, columnar, NoSQL…

## Database Schemas

- Database schema migration is a process of incremental changes to the relational database structure
- The database in the version v1 has the schema defined by the V1_init.sql file. 
- Additionally, it stores the metadata related to the migration process, 
- for example, its current schema version and the migration changelog. 
- When we want to update the schema, we provide the changes in the form of a SQL file, such as V2_add_table.sql. 
- Then, we need to run the migration tool that executes the given SQL file on the database (it also updates the metatables). 
- In effect, the database schema is a result of all subsequently executed SQL migration scripts. Next, we will see an example of a migration.

- Tools and Strategies
    * Upgrade and downgrade: 
        - This approach, for example, used by the Ruby on Rails framework, means that we can migrate up (from v1 to v2) and down (from v2 to v1). It allows the database schema to roll back, which may sometimes end up in data loss (if the migration is logically irreversible)
    * Upgrade only: 
        - This approach, for example, used by the Flyway tool, only allows us to migrate up (from v1 to v2). In many cases, the database updates are not reversible, for example, removing a table from the database. Such a change cannot be rolled back because even if we recreate the table, we have already lost all the data.
    
## Building binaries
    
   - What:
        * the packaged enterprise application in form of an archive
        * includes required dependencies, compile Java sources, and packaged binary classes and other files
        * build systems can publish the artifacts onto an artifact repository 
        * artifact repositories, such as Sonatype Nexus or JFrog Artifactory, save the built artifact versions for later retrieval
   - Why:
        * so that the build pupelines may automatically deploy build artifiacts to test, staging, and prod environments
   - How:
        * built using build systems such as Maven or Gradle, which are installed and executed on the CI server
   - Steps:
        * built using Maven via the command 'mvn package'
        * package phase compiles source, compiles and executes the test sources, and packages the application to a WAR file
        * CI server executes a build system command similar to this to build the artifact in its local workspace directory 
        * artifact can be deployed to an artifact repository using the 'mvn deploy' command,
        * or it will be taken directly from the workspace directory

 ## UI Pattern: Validation Feedback
 
   - What:
    * ex. a warning or suggestion, an error preventing further progress until it’s been fixed, or confirmation that the data was complete and correct
    * validation feedback can indicate 
        * a warning - lets the user continue at their own peril
        * an error - prevents any further progress until it’s been corrected
        * a soft confirmation - encouraging further action to be taken to finish the process
        * a confirmation - assures the user that their work is done
   - Why:    
        * validation feedback pattern increases user’s confidence to the right action (positive feedback) or help them recover from errors (negative feedback)    
   - How:
        * underappreciated form of feedback is a gentle suggestion that hints at better steps rather than prevents further progress
        * Ex. inspecting phone numbers:
            * validating international phone numbers is a notoriously difficult task due variation and formatting
            * when asking for optional phone number, include a validation warning or suggestion when user provides a wrong number 
            * encouraging the visitor to check it, but avoid showing a validation error that prevents task completion
            * visitor proceeds with badly formatted phone number, but were prompted to check it twice for their own benefit
            * For example, consider this message: *Enter your phone number to help fast delivery of your order.*
    
  ## UI Pattern: Autocomplete
  
  - Autocomplete:
    * The autocomplete pattern automatically completes typed user input with matching results from a larger data set
    * autocomplete lets your system match your visitor’s first few key strokes with possible solutions
  - Autosuggestion:
    * Similar to traditional “autocomplete,” “autosuggest” breaks beyond the input provided to suggest alternative, relevant answers
    * It might even suggest results from multiple data sets
    * Google also blends autocomplete and autosuggest by letting you autocomplete the whole sentence using other noun phrases
    * showing additional results below the search input field (emphasizing the available autocomplete text with strong, bold text)
    *  Google’s autosuggest that proposes alternative queries that might be relevant: *“what is europe saying about brexit,”* that can be quite different from the text you’ve typed so far, “What is Brexit EU?”*
