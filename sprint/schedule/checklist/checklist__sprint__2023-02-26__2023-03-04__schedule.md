# Checklist - Sprint: 2023-02-26 - 2023-03-04 - Scheduling tasks on the calendar

# Go through the `pre-mortem` checklist, and create a pre-mortem for the sprint.

- Done

# Calculate the total amount of time in terms of days & hours that realistically have to work on tasks.

- `(2 hours * 5 weekdays`) + `(2 hours * 1 Sunday) + `(4 hours * 1 Saturday)= 16 hours

# Proportion the total time to the "most important objectives that need to accomplish" (from the "clear descriptions of accomplishment & failure" in the `pre-mortem` document).


## Most important element to create:
1. MVP - Form Element
  - 0.3 * 16 hours = ~5 hours
2. MVP - Form data display table
  - 0.15 * 16 hours = ~2.5 hours

3. Administration - Complete Clerky steps (at least upto "Foreign Qualification"
  - 0.1 * 16 hours = ~1.5 hours
4. Administration - Apply for NC "Foreign Qualification"
  - 0.05 * 16 hours = ~1 hour
5. Administration - Update Naksha financial transactions
  - 0.05 * 16 hours = ~1 hour
6. Administration - Spend atleast 30mins on "Trademarks" checklist
  - 0.025 * 16 hours = ~0.5 hours
7. (if time) MVP - user accounts & authentication

Total allocated: 11.5 hours

## Buffer time

- `16 hours - 11.5 hours = 2.5 hours


# With respect to the allocated proportion of the total time break the "most important objectives" down using Dylan Winkle's point estimation work flow so that each task is a maximum of "two days" or "eight hours".

- Try to reasonably fit everything into the allocated time
  - Ask:
    - What is the minimum thing need to build or learn, and focus on creating tasks for that.

## Point estimating: Most import items to create


1. MVP - Form Element (Ability to create arbitrary form elements)
  - Create interface to "create" a form
    - *Accomplishment*:
      - Interface on the web page, that allows users to create a form (with form field data types of: number, text, boolean, (discrete) integer interval (Ex: [-5,5]), categorical
    - *Failure*
      - No web UI that allows users to create a Form that takes those types of measurements as fields
    - **Point estimation**:
      - Workflow:
        - Passes "INVEST" criteria
        - Passes "Is the story size between 1 & 3 points"
        - Passes "Is the acceptance criteria clear enough where no negotiation is needed on the "definition of done"?"
        - Not passes "Is the amount of work needed something that can be done within less than 1 days?"
        - Not passes "Does it require action from an external organization?"
        - Not passes "Does it require completion of another story being worked on by a team member or their collaboration?"
        - Not passes "Does it use data and methodology that is well understod already? Do we have code that does something similar?"
        - Passes "Is a data steward available to guide us or does someone else on the team know the methodology well?"
          - Note:
            - The task to be done is clear enough in terms of generating HTML/JS using Phoenix, and Phoenix is well documented in this regard
        - Passes "Can we estimate how much time it will take to come upto speed on the prior work?"
        - Passes "Can you break down the evaluation of prior work into multiple stories with <3 points each?
      - Result:
        - 3 points (~3 weekdays)
          - 2 points (~2 weekdays): Learning & setting up, Elixir & Phoenix
          - 1 point (~0.5 weekdays): Creating the form element UI
        - Note:
          - Points take into account the reduce hours of "2 hours per weekday"
          - Danger (based on point allocation) of work overflowing the allocated time of ~5 hours
  - Display the form in the "application"
    - *Accomplishment*
      - Form created by the user displayed in the "application" section of the "Data Collection" project
    - *Failure*
      - Not that

  - Store form data in a table in a mock database for unit testing
    - *Accomplishment*:
      - Data inputted through the form in the "Application" section, stored into a mock database for unit testing
      - Automatically add a timestamp field for when the data was inputted
    - *Failure*
      - Not even a data model on the front end side created (the between form data inputted & stored in the data set)
      - No data saved in a temporary "database" for unit testing purposes

## Prioritize the "most important objectives" so that the "minimum" items can be reasonably accomplished.



# Place the tasks into the calendar in at most "two hour time blocks" (prioritized by most important to least important)

