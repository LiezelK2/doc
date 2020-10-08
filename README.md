# Documentation for the P&D file
The purpose of the Package and Deployment file is to provide a template for ease of use when creating K2 smartforms for Sharedo.

## How to use the form


## How to update the form


## Smartform Rules

### ShareDo.Templates.Form.SaveAsForm Overview

The form has two rules: 
1. When the Form is Initializing
2. When the server loads the Form

<img src="https://github.com/LiezelK2/doc/blob/main/images/rulesOne.PNG" width="500">

#### When the Form is Initializing
<img src="https://github.com/LiezelK2/doc/blob/main/images/formInit.PNG" width="900">
When the form is initialized, it executes the initialize method for the Sharedo.Templates.ItemView.MainView view

#### When the server loads the Form
<img src="https://github.com/LiezelK2/doc/blob/main/images/serverloadsForm.PNG" width="900">
This rule executes the server rule of the Sharedo.Templates.ItemView.MainView view which imports the CSSText control, providing the sharedo styling for the smartform and the scripting for the post message that is received from Sharedo

### ShareDo.Templates.ItemView.MainView
