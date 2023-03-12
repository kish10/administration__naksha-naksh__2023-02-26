# MVP Specification - Created 2023-02-26

**Deadline**: 2023-03-11

## MVP Features

- App on server, so interactions through a browser
- Be able to login & have state associated to the account
- Be able to create a "data collection" project
- Be able to create an arbitrary form
  - Which:
    - Creates a (manual data input) form UI with the desired fields
      - Supported form field data types are: numbers, text, boolean, category
    - Creates a table in the backend that matches the form fields (stores form data in the database)
- Be able to view stored form data
  - So simple view "Table" element, that displays the form data as a table, chronologically, with vertical scroll ability.
