Readme.txt

Lotus Notes Data Exporter

Consists of a number of Lotus Notes Script Agents solving different tasks of data analysis and export from various Lotus Notes versions. More troughout documentation of the inividual scripts and how to install, edit parameters and rund the script in a Lotus Notes Agent can be found in the doc-section of Lotus Notes Data Exporter.

Available Lotus Notes Script Agents:
A_xmlExport.txt - XML/TXT export.
B_dxlExport.txt - DXL export.
C_xmlExportForm.txt - Database Analyse (and later form-based or custom export).

Scripts to be released later on:
D_analyseDatabase.txt - DB analyse of Lotus Notes docs, fields, forms etc (types & counters).


Parameter settings in the Lotus Notes script agent may need to be edited:

Regarding what to edit, you will see it quite well commented.
You will have to set the export target and that target must be prepared (create folders)

	exportTarget = |C:\Export\LotusNotes\|   
	
This you can set to what suits you, like f:\myexport\project1\ or what ever.
Just know that the path must work before you run the script.

You dont really have to set anything else, but you can.

When the settings are changed, find the agent in the agent list.
(Left click on the agents in the designer).

Then you can right click and choose "Run".
Look at your cpu and target folder, an export should appear :-)

-- Enjoy!