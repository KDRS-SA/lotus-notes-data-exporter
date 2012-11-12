Readme.txt

1. To add the Lotus Notes Data Exporter to your databases, first fire up the Lotus Notes Workspace.
2. Find a database and open it in the designer.
3. Open up the tree structure [+]Shared code -> [+]Agents
4. Click on Agents
5. Click on "New agent"
6. In the upper part of the dialog, enter a name (for instance doExport).
7. In the runtime part of the dialog, change "Agent list selection" in the upper drop down
8. Go to the key/security tab of the Agent property window.
9. Click the blue button "Run on behalf of" and choose a db admin user
10. Set runtime security level to 3
11. Save the agent (CTRL+S)
12. Edit the agents details

Regarding what to edit, you will see it quite well commented.
You will have to set the export target and that target must be prepared (create folders)

	exportTarget = |D:\Byarkiv\Eksport\|   
	
This you can set to what suits you, like f:\myexport\project1\ or what ever.
Just know that the path must work before you run the script.

You dont really have to set anything else, but you can.

These settings can be changed
	exportXML = True 					' Set to true if you want 1 XML per database		- rec.: True
	exportTXT = True					' Set to true if you want 1 TXT per database		- rec.: True
	exportDXL	 = False					' Dump db to DXL (FULL XML DUMP) 			- rec.: True
	
'# These apply for 1% of the users (much more work in the following migration steps)  	
	exportTXT11 = False				' Set to true if you want 1 TXT per document 		- rec.: False
	exportXML11	= False 				' Set to true if you want 1 XML per document 	- rec.: False	
	
'# Export empty tags? 
	exportEmptyTags = True			' Huge dumps may need this set to false			- rec.: True
	exportAttachments = True		' Your files/attachments, if any in the db.			- rec.: True

	
And you can set the subfolders too! (they will be created by the script, if they are needed (depends on your settings))

	xmlFolder = |xml|								' For XML files 
	txtFolder = |txt|									' For TXT files
	dxlFolder = |dxl|									' For DXL dump of db
	attachmentFolder = |filer|					' For attachments / files
	logFolder = |logg|								' For logs (error and result)
	
Also you might want to change theese settings:

	strErrorLogName = |avvik|					' The error log file name "error" (will only log when errors>0)
	strResultsLogName = |resultater|			' The results log file name "results" (will log documents, attachments and number of errors)
	strExportLogName = |instillinger|			' The export settings log file name, will log boolean values,etc.
'# Logging, field names	
	strRecordsTxt = |Dokument|				' The text for documents in the log file, also used in the XML "Documents"  
	strAttachmentTxt = |Filer|						' The text for Attachments/files in the log file "Files"
	strErrorTxt = |Feil|								' The text for Error in the log file "Errors"
	strOnLineTxt = |på linje|						' For error logging "on line"
	strInTxt = |i|										' For error logging "in" (error in)
	
That's all for now.

When the settings are changed, find the agent in the agent list.
(Left click on the agents in the designer).

Then you can right click and choose "Run".
Look at your cpu and target folder, an export should appear :-)

-- Enjoy!