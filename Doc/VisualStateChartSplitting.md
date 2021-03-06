# How to split State Chart without using \<invoke\>

SCXML has an option to split state machine into sub state machines using \<invoke\> element. But in this case we need to provide data sharing between all parts.
This procedure in some cases may be redundant or complex. And not all SCXML SDKs support such feature.
But what to do if state chart becomes too large and difficult to read?

Let's take a look at [QT pinball state chart example](https://doc.qt.io/qt-5/qtscxml-pinball-example.html)
![pinball](https://github.com/alexzhornyak/ScxmlEditor-Tutorial/blob/master/Images/VisualSplitting_Intro.png)

We see that state **global** could be splitted into **guiControl** and **internalState**

## Converting states to virtual sub states
Select state that you wish to make virtual, press right mouse button and select in the popup-menu **Convert To->Virtual**
![convert](https://github.com/alexzhornyak/ScxmlEditor-Tutorial/blob/master/Images/VisualSplitting_ConvertToVirtual.png)

This operation will create virtual state machine unit and move selected state machine logic to the new one
![virtual_unit](https://github.com/alexzhornyak/ScxmlEditor-Tutorial/blob/master/Images/VisualSplitting_VirtualUnit.png)

Save the unit with the corresponding name.
We recommend to give prefix like **include_** or **virtual_** for better understanding of project unit roles.

![virtual_unit_save](https://github.com/alexzhornyak/ScxmlEditor-Tutorial/blob/master/Images/VisualSplitting_VirtualUnitSave.png)

Do the same procedures for other units you'd like to make virtual
![convert2](https://github.com/alexzhornyak/ScxmlEditor-Tutorial/blob/master/Images/VisualSplitting_ConvertToVirtual2.png)

Also save the new virtual unit and give the same prefix
![save2](https://github.com/alexzhornyak/ScxmlEditor-Tutorial/blob/master/Images/VisualSplitting_VirtualUnitSave2.png)

After splitting you may reduce the width and height of virtual state chart shapes
![after_split](https://github.com/alexzhornyak/ScxmlEditor-Tutorial/blob/master/Images/VisualSplitting_AfterSplit.png)

## Splitting of virtual units
Procedures for splitting virtual units are the same as procedures made for root state machine
![level2](https://github.com/alexzhornyak/ScxmlEditor-Tutorial/blob/master/Images/VisualSplitting_SplitLevel2.png)

After splitting virtual unit will be marked. And nested virtual state chart shapes will have a links to the corresponding virtual units.

![level2_after_split](https://github.com/alexzhornyak/ScxmlEditor-Tutorial/blob/master/Images/VisualSplitting_internalState.png)

## Debugging
Set SCXML unit which will be as root

![root_for_run](https://github.com/alexzhornyak/ScxmlEditor-Tutorial/blob/master/Images/VisualSplitting_RootForRunAndBuild.png)

Choose layout that will be more suitable for you during debugging
![layout](https://github.com/alexzhornyak/ScxmlEditor-Tutorial/blob/master/Images/VisualSplitting_Layout.png)

After run all entered states will be highlighted
![debug1](https://github.com/alexzhornyak/ScxmlEditor-Tutorial/blob/master/Images/VisualSplitting_Debug1.png)

You may double click on virtual shape to switch to the its source unit
![debug2](https://github.com/alexzhornyak/ScxmlEditor-Tutorial/blob/master/Images/VisualSplitting_Debug2.png)
