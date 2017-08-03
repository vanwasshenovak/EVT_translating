# Readme

When modifying the transcription in the 238.xml file
1. Before Transform - duplicate output_data file to output_data copy
2. Apply transformation to 238.xml file
3. Open structure.xml in output_data file and structure.xml in output_data copy files.
4. Copy the editions from the structure.xml file in the duplicate file to the new one
5. Update the sound tags in page_fol_2r_diplomatic.html from the older file in output_data copy.

Translations were added based on the EVTFAQ.pdf page 3: 
There is another way to do the trick, that is faster but less optimal and involves manual changes to the output data:
-modify the structure.xml file in the output folder adding a new <edition> element after the other;
-add the html files with the translation in the proper folder, that is /data/output/ translation/ (the folder name needs to be the same you used in the <edition> element, all lower case); the content you want to be displayed needs to be inserted in this structure, otherwise it won't work:
```<div id="text_frame">
<div id="text">  [your translation]  </div> </div>```
-name every file in the proper way: page_*xml:id*_translation.html (the *xml:id* value refers to the @xml:id attribute of the relative <pb>);
-make a backup of these files because every time you will launch the XSLT transformation the entire output folder will be overwritten.
It is not optimal, since every new edition building will overwrite the data/output folder, but for the it is probably the faster way if you prefer not to add your own XSLT templates.
