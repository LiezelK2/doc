# K2 ShareDo Theme

## Documentation for the P&D file
The purpose of the Package and Deployment file is to provide a template for ease of use when creating K2 smartforms for Sharedo.

## How to use the form
After you've installed the Kspx package, go to the Sharedo folder, and open Templates.
Select the ShareDo.Tmeplates.Form.SaveAsForm form, select the Save As function to copy the form.

<img src="https://github.com/LiezelK2/doc/blob/main/images/saveAs.PNG" width="500">

Please take note that you should not clone the views, this rule must always be set to No.






## How to add custom theming to your form:
1. Open **./release/Merged.html**
2. Copy the contents of the file
3. Create View on SF Designer (For Ref purposes call it **ShareDo Theme**)
4. Add a DataLabel
5. :heavy_plus_sign: Add a server event rule `When the server loads the View`
6. Set the Control Properties of DataLabel using `Set a control's properties` and pressing `(configure)` :gear: 
7. Paste the copied contents (copied from point 5) into the text value in the rule
8. **Check** the `Literal` property so that it applies **yes** (or true)
9. Save and check in the View.
      - At this point you are finished with this view and the "theme" can be added to all your SmartForms Forms for use.
      - **Repeat step 10 to end for each SF Form you want to apply the "theme" to.**
10. Include the view in a SmartForm Form to use.
      - You can add the views you want styled with the theme here or chose a Form that already has Views on it you want styled.  
      - **Note: This theme is designed to override the *Lithium Theme* on the Form and so not setting the theme to `Lithium` on the form may have undesired or expected results.**
11. :heavy_plus_sign: Add Event/Form rule `When the server loads the Form`, action of `then execute the When the server loads` **ShareDo Theme** `View server rule`
12. Save the changes and the form.
  
Use or test the Form, adding controls and views as required.

### To Regenerate or update theme:
1. Ensure Node JS is installed and VS Code
2. Open the folder with VS Code
3. Open the command line in VS Code and run `npm start`
4. Follow the Apply process above as required.
      - i.e. If you just want to update the theme on a K2 SF Environment, just edit the theme View, save and check-in.
      - Follow entire Apply process when no theme view exists.

## Additional Styling
### Labels
  - Append `ShareDoRegular` to each label you want displayed normally instead of the normal ShareDo Bold label.  
    `My label ShareDoRegular` or `My labelShareDoRegular` or  `label_ShareDoRegular` will all work.



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
<img src="https://github.com/LiezelK2/doc/blob/main/images/loadview.PNG" width="900">

It is important to remember that this rule should not be changed

#### 2. When txtFrameMessage is Changed
<img src="https://github.com/LiezelK2/doc/blob/main/images/textFrame.PNG" width="500">

This rule allows for the advanced conditions, and calls the @shareDo or @shareDo_SendClose depending on the condition set

#### 3. [override] @shareDo_Save
<img src="https://github.com/LiezelK2/doc/blob/main/images/sharedoSave.PNG" width="900">

With this rule, you can place your save mechanism in here to override the rule

#### 4. @shareDo_SendClose
<img src="https://github.com/LiezelK2/doc/blob/main/images/sharedoSendClose.PNG" width="900">
