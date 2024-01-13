# MagSus Correction_V3

<procedure title="Workflow for MagSus Correction" collapsible="true">
    <code-block lang="mermaid">
        stateDiagram-v2
       [*] --> MAG
       MAG: Magnetic Susceptibility needs to be corrected
       RR: Export .las file
       NU: Get the slope
       MS: Modify the slope
       AC: Create new formula log on WellCAD and use the slope
       VL: Import .las file in ViewLog 4
       LGTM: All good
       RP: Ready to add it in the Draft plot
       MAG --> RR
       RR --> VL
       VL --> NU
       NU --> AC
       AC --> Review
       Review --> MS
       MS --> Review
       Review --> LGTM
       LGTM --> RP
       RP --> [*]
</code-block>
    
</procedure>

<procedure title="Step by Step: How to correct the Magnetic Susceptibility" collapsible="true">
<format style="bold" color="Orange">How to visualize if the Magnetic Susceptibility needs to be corrected?</format>

-	We need to visualize the Magnetic Susceptibility on a high scale.
     MagSus curve should be a straight line when we visualize it on a high scale, in this plot we can see that the line has an inclination.


<img src="Original_MagSus.png" width="250" alt="Original_MagSus" border-effect="line"/>

<procedure title="Importing MagSus on VIEWLOG 4" id="inject-a-procedure" collapsible="true">
<format style="bold" color="Orange">Correcting MagSus:</format>
<format style="bold" color="DarkSlateBlue">Importing MagSus on VIEWLOG 4</format>
    <step>
        <p>Export the MagSus <path>.las</path> file in a folder:</p>
            <p>a.	File -> Export -> Single File -> Save -> OK</p>
    </step>
    <step>
        <p>Open “VIEWLOG 4” software:</p>

<p>a.	Double click on “VIEWLOG 4” software</p>

<p>b.	Click on “Continue in Demo/Data Browser Mode”</p>

<p>c.	Create a new file: Click on "New”</p>

<p>d.	Import the <path>.las</path> file: File ->  Import ->  Select File ->  Open -> Import -> Import -> OK -> OK</p>

<img src="ViewLog_2.png" alt="Alt text" width="500" border-effect="line"/> 

<img src="ViewLog.png" alt="Alt text" width="300" border-effect="line"/>

<format style="bold" color="Black">Sample MagSus Plot:</format>

<img src="MagSus_ViewLog.png" alt="Alt text" width="300" border-effect="line"/>
    </step>

<procedure title="Getting the slope" id="Getting_the_slope" collapsible="true">
<format style="bold" color="Orange">Correcting MagSus:</format>
<format style="bold" color="DarkSlateBlue">Getting the slope</format>
    <step>
        <p>It's necessary to obtain the slope of the curve:</p>
            <p>a.	Display the statistics information: Click on Interpret -> Statistics</p>
            <p>b.	Populate the statistics information: Click on the top of the trace and drag to the bottom of the trace (a green line should appear on the trace and the stats box populated should appear at the end of the window)</p>
<img src="ViewLog_Slope.png" alt="Alt text" width="500" border-effect="line"/>
    </step>
    <step>
        <p>Copy the slope to apply it on WellCAD</p>
            <p>a. Click on “Slope” and then click on “Save”</p>
    </step>

</procedure>

<procedure title="Correcting de inclination" id="Correcting_Inclination" collapsible="true">
<format style="bold" color="Orange">Correcting MagSus:</format>
<format style="bold" color="DarkSlateBlue">Correcting de inclination</format>
    <step>
        <p>Open a new sheet in Excel and paste the “Slope”:</p>
<img src="Excel_Slope.png" alt="Alt text" width="250" border-effect="line"/>
    </step>
    <step>
        <p>Create a new “Formula Log”:</p>

<p>a.	Click on Edit -> Insert New Generic Log… -> Formula Log</p>

<img src="WellCAD_New_Formula.png" alt="Alt text" width="300" border-effect="line"/>

<p>b.	Add the next formula:</p>


<code-block lang="tex">
    \begin{equation}
    {MAGSUS}-({SLOPE}*{DEPTH})
    \end{equation}
</code-block>
    </step>

>Select the corresponding logs in the Formula Log window and copy the slope from the Excel we created in the previous step.
>
{style="tip"}

<img src="Formula_Log.png" alt="Alt text" width="300" border-effect="line"/>

<format style="bold" color="Black">Sample MagSus corrected plot:</format>

<img src="MagSus_Corrected.png" alt="Alt text" width="300" border-effect="line"/>

>Note: If the trace is still inclined, you can adjust the slope to have a straight line.
>
{style="tip"}
</procedure>
</procedure>


