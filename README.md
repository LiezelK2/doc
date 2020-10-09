# Documentation for the P&D file
The purpose of the Package and Deployment file is to provide a template for ease of use when creating K2 smartforms for Sharedo.

## How to use the form
After you've installed the Kspx package, go to the Sharedo folder, and open Templates.
Select the ShareDo.Tmeplates.Form.SaveAsForm form, select the Save As function to copy the form.

<img src="https://github.com/LiezelK2/doc/blob/main/images/saveAs.PNG" width="500">

Please take note that you should not clone the views, this rule must always be set to No.

## How to update the form


## Smartform Rules

### ShareDo.Templates.Form.SaveAsForm Overview

The form has two rules: 
1. When the Form is Initializing
2. When the server loads the Form

<img src="https://github.com/LiezelK2/doc/blob/main/images/rulesOne.PNG" width="500">

#### 1. When the Form is Initializing
<img src="https://github.com/LiezelK2/doc/blob/main/images/formInit.PNG" width="900">
When the form is initialized, it executes the initialize method for the Sharedo.Templates.ItemView.MainView view

#### 2. When the server loads the Form
<img src="https://github.com/LiezelK2/doc/blob/main/images/serverloadsForm.PNG" width="900">
This rule executes the server rule of the Sharedo.Templates.ItemView.MainView view which imports the CSSText control, providing the sharedo styling for the smartform and the scripting for the post message that is received from Sharedo

### ShareDo.Templates.ItemView.MainView
The view contains four rules:
1. When the server loads the View
2. When txtFrameMessage is Changed
3. [override] @shareDo_Save
4. @shareDo_SendClose
<img src="https://github.com/LiezelK2/doc/blob/main/images/viewRulesOverview.PNG" width="500">

#### 1. When the server loads the View
<img src="https://github.com/LiezelK2/doc/blob/main/images/loadview.PNG" width="500">

It is important to remember that this rule should not be changed

#### 2. When txtFrameMessage is Changed
<img src="https://github.com/LiezelK2/doc/blob/main/images/txtFrame.PNG" width="500">

#### 3. [override] @shareDo_Save
<img src="https://github.com/LiezelK2/doc/blob/main/images/sharedoSave.PNG" width="500">

With this rule, you can place your save mechanism in here to override the rule

#### 4. @shareDo_SendClose
<img src="https://github.com/LiezelK2/doc/blob/main/images/sharedoSendClose.PNG" width="500">
