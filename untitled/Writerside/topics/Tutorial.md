# MagSus Correction


<format style="bold" color="Orange">How to visualize if the Magnetic Susceptibility needs to be corrected?</format>

-	We need to visualize the Magnetic Susceptibility on a high scale.
     MagSus curve should be a straight line when we visualize it on a high scale, in this plot we can see that the line has an inclination.


<img src="Original_MagSus.png" width="250" alt="Original MagSus" border-effect="line"/>


<format style="bold" color="Orange">Correcting MagSus:</format>
<format style="bold" color="DarkSlateBlue">Importing MagSus on VIEWLOG 4</format>



1.	Export the MagSus .las file in a folder:

      a.	File -> Export -> Single File -> Save -> OK

2. Open “VIEWLOG 4” software:

         a.	Double click on “VIEWLOG 4” software

         b.	Click on “Continue in Demo/Data Browser Mode”

         c.	Create a new file: Click on "New”

         d.	Import the .las file: File ->  Import ->  Select File ->  Open -> Import -> Import -> OK -> OK

<img src="ViewLog_2.png" alt="Alt text" width="500" border-effect="line"/> 

<img src="ViewLog.png" alt="Alt text" width="300" border-effect="line"/>

<format style="bold" color="Black">Sample MagSus Plot:</format>

<img src="MagSus_ViewLog.png" alt="Alt text" width="300" border-effect="line"/>


<format style="bold" color="Orange">Correcting MagSus:</format>
<format style="bold" color="DarkSlateBlue">Getting the slope
</format>

1.	It’s necessary to obtain the slope of the curve:

            a.	Display the statistics information: Click on Interpret -> Statistics

            b.	Populate the statistics information: Click on the top of the trace and drag to the bottom of the trace (a green line should appear on the trace and the stats box populated should appear at the end of the window).

            c.	Copy the slope to apply it on WellCAD: Click on “Slope” and then click on “Save”.

<img src="ViewLog_Slope.png" alt="Alt text" width="500" border-effect="line"/>

<format style="bold" color="Orange">Correcting MagSus:</format>
<format style="bold" color="DarkSlateBlue">Correcting de inclination</format>

1.	Open a new sheet in Excel and paste the “Slope”:

<img src="Excel_Slope.png" alt="Alt text" width="250" border-effect="line"/>


1. Create a new “Formula Log”:

            a.	Click on Edit -> Insert New Generic Log… -> Formula Log

<img src="WellCAD_New_Formula.png" alt="Alt text" width="300" border-effect="line"/>

            b.	Add the next formula: 

    {MAGSUS}-{SLOPE}*{DEPTH}




>Select the corresponding logs in the Formula Log window and copy the slope from the Excel we created in the previous step.
>
{style="tip"}

<img src="Formula_Log.png" alt="Alt text" width="300" border-effect="line"/>

<img src="MagSus_Corrected.png" alt="Alt text" width="300" border-effect="line"/>

>Note: If the trace is still inclined, you can adjust the slope to have a straight line.
>
{style="tip"}


<seealso>
<!--Give some related links to how-to articles-->
</seealso>
