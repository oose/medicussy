MagicDraw/Cameo/Magic Modeler mdzip-files with the imported RAAML.xmi files from the OMG website. This had to be done in order to use them in our project.

## How these were produced
Do the following in the order of the dependencies.
- open the xmi as project in MagicDraw (we used 19.0 SP3)
- An error message will tell you, that some used projects are not found. Select them manually and use the MagicDraw Versions (either in \profiles or \libraries).
- Share the one folder that is in the xmi (for profiles this is done automatically)
- Save the project as mdzip
- Move the xmi to another folder, so that the next file processed will load the mdzip instead of the xmi


Special treatment for CoreRAAML.xmi: It doesn't find the imported package SysML. We tell it to look for it in the Cameo profiles. It also makes it a used project. However, we still get a message, that the project is corrupted. In fact, the package import is still missing its target. Therefore, all generalizations to SysML stereotypes are missing. We didn't find any way to tell Cameo where it is (the URI is different, but changing it, doesn't help). Therefore we had to manually set the imported package and add the three missing generalizations. Hopefully this was all there is.


What doesn't work:
Opening the xmi-files without converting them to mdzip. Then FMEA.xmi will create a mysterious error message.
