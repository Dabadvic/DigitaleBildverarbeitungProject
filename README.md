# DigitaleBildverarbeitungProject
Project for the course Digitale Bildverarbeitung at HTWK Leipzig consisting of: Plugin of ImageJ for classification and extraction of reference patterns. Made in collaboration with other two students: Felix Hain and Jose Ortega Valiente.

##Basic user's guide

First, the user needs to have installed ImageJ and copied the plugin in the plugin's folder of the
program.
Using the command line, we have to locate ourselves in the folder where ImageJ is installed (Windows users) and once there use the command provided for running the plugin, which is:
  >  imagej -eval "run('Symbol_Recognition', 'parameters');"
  
You can add the option -batch at the end, so ImageJ executes without a GUI.

Replace the word parameters with any of the following options:
* No parameters: This takes a default input and output path inside the project plugin.
  * Parameters:
    * input=[path]
      * (replace [path] with an actual path) the input path, where the program will take the image from, it can be both, a picture or a folder. In the second case, the program takes all the pictures in the folder.
    * output=[path]
      * (replace [path] with an actual path) the output path, where the program will put the resulting pictures.
    * recursive
      * when this option is specified, the program will look for images in all the folders within the input path.
    * logdetails
      * with this option specified, the program will activate the log messages.

To set multiple parameters at once, separate them with a pipe symbol “|”.
The order of the parameters does not affect the program, they can be introduced in any order as long as the name is correctly written.
If the input path is not specified, it defaults to a folder named “input” inside the folder of this plugin. The same happens with the output path.

Example:
> imagej -eval "run(' Symbol_Recognition', 'input=C:/images|recursive');"

The supported image formats are: .tiff, .bmp, .dicom, .fits, .pgm, .gif, .jpeg, .png
If a file format is not supported during a scan, the file will be skipped and the scan will continue in search of compatible formats.

How to get the best results:
* The image should already be binarized.
* Clean scan, the image should be mostly free from imperfections (like noise or small pixels).
* The image must be right side up and should be straight, so the text describes a horizontal
line.
* There should not be any noise at the sides of the image.
