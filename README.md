
# Mweb
 Mweb, a simple html extension that uses json and C#
# Usage Guide
 Example project can be cloned from this repo, or found under [INSTALL LOCATION]/Examples/ if installed via installer
 ### Folder Setup

  Your project needs to contain two files: <br><pre>
   -[page-name].mweb (can have multiple) <br>
   -[project-name].json (can have multiple, but have a single file is recomended)<br></pre>
  Example: <br><pre>
   example project/<br>
               -- example.mweb<br>
               -- exampleProj.json<br></pre>
 
 ### Json Setup  
 Your json file should contain all your aspects that you are going to use across all your .mweb pages in your project<br>
 Required Apects:<pre>
    {
        "aspect": "^System",
        "code": [ "PATH\\TO\\CSS\\styles.css", "PATH\\TO\\IMAGES\\FOLDER\\[entire folder]", "PATH\\TO\\JS\\[enitre folder]", ".fileExtentionType" ] *Must be in this order, must be the first aspect
    },
    {
        "aspect": "^html",
        "code": [ "<!DOCTYPE html>", "<html>" ] *THIS IS THE HTML PAGE HEADING CODE
    },
    {
        "aspect": "^head",
        "code": [ "<head>", "<link rel='stylesheet' href='mystyle.css'>", "<link rel='icon' type='image/x-icon' href='http://mweb.maxinc.cf/logo.ico'>", "<meta name='viewport' content='width=device-width, initial-scale=1.0'>", "<title>Mweb 1.0</title>", "</head>" ] *note the the css is different from the ^system aspect, this is becuase the system aspect uses css in a way to include your style sheet when displaying the debugable html page rather then the exported one
    },
 </pre>
  How aspects work:<pre>
  [
   {
        "aspect": "^Aspect 1", *Apect's name, called in mweb file exactly the same (^Aspect 1)
        "code": [ "Line 1", "Line2" ] *Every line of code for this aspect
    },  
    {
        "aspect": "^Aspect 2",
        "code": [ "Line 1", "Line 2" ] 
    },
  ]
  </pre>
 Example Apects:<pre>
 [
    {
        "aspect": "^System",
        "code": [ "C:\\Users\\98max\\OneDrive\\Documents\\Examples\\Exported\\mystyle.css", "C:\\Users\\98max\\OneDrive\\Documents\\Examples\\Exported\\Images\\", "path/to/js[enitre folder]", ".htm" ]
    },
    {
        "aspect": "^html",
        "code": [ "<!DOCTYPE html>", "<html>" ]
    },
    {
        "aspect": "^head",
        "code": [ "<head>", "<link rel='stylesheet' href='mystyle.css'>", "<link rel='icon' type='image/x-icon' href='http://mweb.maxinc.cf/logo.ico'>", "<meta name='viewport' content='width=device-width, initial-scale=1.0'>", "<title>Mweb 1.0</title>", "</head>" ]
    },
    {
        "aspect": "^header",
        "code": ["<div","class='header'>","","<p>A","<b>responsive</b>","html","extentsion","in","C#.</p>","</div>"]
    {
        "aspect": "^navbar",
        "code": ["<div","class='navbar'>","<a","href='#'","class='active'>Home</a>","<a","href='/download/'>Download</a>","<a","href='#about'>About</a>","<a","href='https://maxinc.cf/'","class='right'>MaxInc</a>","</div>"]
    },
        {
        "aspect": "^body",
        "code": [ "<body>" ]
    },
    {
        "aspect": "^footer",
        "code": ["<div","class='footer'>","MWEB 1.0 by Max Tyson","</div>"]
    },
    {
        "aspect": "^end",
        "code": [ "</body>", "</html>" ]
    }
]
 </pre>
 ### mweb Setup  
 To run your project with commands open a cmd window and type [path/to/.mweb] -[command] (list of commands can be shown via command -help)
