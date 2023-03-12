# Checklist - Sprint: 2023-02-26 - 2023-03-04 - MVP Form element

## UI that allows users to create an arbitrary form

### (rough) MVP while learning Phoenix & Elixir

1. Determine where to add "HTML" code in Phoenix for the UI
  - 2023-02-26:
    - Identified that for now will put the html code in `naksh_dc/lib/naksh_dc_web/dc_project_html/dc_project.html.heex`
      - Where that file is rendered through: `naksh_dc/lib/naksh_dc_web/controllers/dc_project_controller.ex`

2. Determine what the user UI creation UI would look like (in terms of HTML/JS) -- Could be super basic, like only has the basic elements of (form field name, form field type specified as text or simple buttons)
  - 2023-02-26:
    - Made a rough wireframe that detailed the "html" components needed (& some Phoenix parts)

3. Implement that basic rough UI in Phoenix
  - 2023-02-28 (7:00):
    - Resolved blocker:
      - Figured out how to enable client side interativity in Phoenix using `LiveView JS`
        - This helps overcome blocker of how to make the:
          - HTML button "Add a new field" clickable (since can't add the "onClick" attribute like do with Javascript interactive buttons)

  - 2023-02-28 (7:30):
    - Hit blocker:
      - Although know how to make the "Add a new field" button clickable -- (in Phoenix) don't know how to insert the HTML code for the "form field" row (i.e. the UI component where the user can specify the name & measurement type of the new field)

  - 2023-02-28 (20:19):
    - Idea to resolve blocker:
      - Want to do something similar to Svelte (but maybe with Phoenix better to stick to server side (instead of generating JS code with Phoenix to run client side).
        - Since:
          - Server side seems like the path of least resistance in Phoenix at the moment
          - Eventually want to hook into server side processes, such as database storage -- so can wait to make server-side vs client-side decistion then
        - Idea:
          - Make the "Add a new Form Field", button call a function on the server side, that adds a "default"/"empty" form field to an Elixir variable/list that holds the "Form fields" in that "Form"
          - Populate the "Form" field rows in the HTML view, based on an Elixir variable/list that is tracked server side
            - So this becomes like in Svelte:
              - ```
                <#each formFieldInfoList as formFieldInfo>
                  <ul>
                    <FormFieldComponent props={info=formFieldInfo}/>
                  </ul>
                </each>
                ```
              - Where in this case, the `formFieldInfoList` is created & updated on the server side, and rendered on the client side.
        - Potential steps to recreate this in Phoenix:
          - 1. Create a list of form fields in the controller to pass as within the `assign` parameter in the View definition (can use "dc_project_controller" for now)
            - See example of the `greet` function is created in:
              - https://hexdocs.pm/phoenix/components.html#function-components
          - 2. Pass the list to the HTML template as variable added to the "assigns" parameter
            - (similar to how `messenger` was passed at the end of the "Reuqest-life-cycle' chapter.)
          - 3. Loop through the variable creating lists:
            - See example in:
              - https://hexdocs.pm/phoenix_live_view/Phoenix.Component.html#module-the-default-slot

  - 2023-03-01:
    - Resolving blocker of how exactly to implement the HTML UI part of "allow user to create an arbitrary form":
      - Now know how to mimick the similar Svelte code (except logic is executed server-side for now):
        - 1. Define a variable to store & update the list of "form fields" with an arbitrary form, inside the `dc_project_controller.ex` (for now).
        - 2. Pass the variable as a part of the `assigns` parameter in the `render/3` function call, inside the controller `action` that renders the `dc_project_html.ex` *template* (in future can switch to a more specific action if necessary -- or a more specific variable, if for example there are many independent forms within an "Application")
        - 3. Define a function component inside `dc_project_html.ex` *template*, that would render the `Form fields` in the "Edit" section of the "dc_project", so that a user can create an arbritrary "Form" based on the "Form fields".
          - The action component should:
            - Have an `attr` call declared before the function component definition, that indicates that the component requires a list of "Form fields"
          - Loop through the "form field" list, and create the "Form Field" rows in "Edit mode"
            - Can create another function component that renders a "Form field" that is "Editable" -- and render that inside the loop

  - 20230-03-01:
    - Update:
      - Able to render a "Form field" name & measurement type in text, through phoenix
        - Just testing how to render
          - So even the measurement type is just specified from a "text" field, in a unchangable "form_field_list"
    - Next steps:
      - A single form field creation:
        - Allow the user to input a name
        - Create buttons for measurement types
        - Put a "submit form field" button, to save the form field
      - Make the "Add a new field" button to generate UI to specify a new form field
