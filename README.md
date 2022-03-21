
# Mweb
 Mweb, a simple html extension that uses json and C#
# Usage Guide
 Example project can be cloned from this repo, or found under [INSTALL LOCATION]/Examples/ if installed via installer
 On any example code/required igore the *and text follwing as its comment code
 ### Folder Setup

  Your project needs to contain two files: <br><pre>
   -[page-name].mweb (can have multiple) <br>
   -[project-name].json (can have multiple, but have a single file is recomended)<br></pre>
  Example: <br><pre>
   example project/<br>
               -- example.mweb<br>
               -- examplePage2.mweb<br>
               -- exampleProj.json<br></pre>
 
 ### Json Setup  
 Your json file should contain all your aspects that you are going to use across all your .mweb pages in your project<br>
 Required Apects:<pre>
    {
        "aspect": "^System",
        "varibles": [ "&none" ],
        "code": [ "PATH\\TO\\CSS\\styles.css", "PATH\\TO\\IMAGES\\FOLDER\\[entire folder]", "PATH\\TO\\JS\\[enitre folder]", ".fileExtentionType" ] *Must be in this order, must be the first aspect
    },
    {
        "aspect": "^html",
        "varibles": [ "&none" ],
        "code": [ "<!DOCTYPE html>", "<html>" ] *THIS IS THE HTML PAGE HEADING CODE
    },
    {
        "aspect": "^head",
        "varibles": [ "&none" ],
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
        "varibles": [ "&none" ],
        "code": [ "C:\\Users\\98max\\OneDrive\\Documents\\Examples\\Exported\\mystyle.css", "C:\\Users\\98max\\OneDrive\\Documents\\Examples\\Exported\\Images\\", "path/to/js[enitre folder]", ".htm" ]
    },
    {
        "aspect": "^html",
        "varibles": [ "&none" ],
        "code": [ "<!DOCTYPE html>", "<html>" ]
    },
    {
        "aspect": "^head",
        "varibles": [ "&none" ],
        "code": [ "<head>", "<link rel='stylesheet' href='mystyle.css'>", "<link rel='icon' type='image/x-icon' href='http://mweb.maxinc.cf/logo.ico'>", "<meta name='viewport' content='width=device-width, initial-scale=1.0'>", "<title>Mweb 1.0</title>", "</head>" ]
    },
    {
        "aspect": "^header",
        "varibles": [ "&none" ],
        "code": ["<div","class='header'>","","<p>A","<b>responsive</b>","html","extentsion","in","C#.</p>","</div>"]
    {
        "aspect": "^navbar",
        "varibles": [ "&none" ],
        "code": ["<div","class='navbar'>","<a","href='#'","class='active'>Home</a>","<a","href='/download/'>Download</a>","<a","href='#about'>About</a>","<a","href='https://maxinc.cf/'","class='right'>MaxInc</a>","</div>"]
    },
        {
        "aspect": "^body",
        "varibles": [ "&none" ],
        "code": [ "<body>" ]
    },
    {
        "aspect": "^footer",
        "varibles": [ "&none" ],
        "code": ["<div","class='footer'>","MWEB 1.0 by Max Tyson","</div>"]
    },
    {
        "aspect": "^end",
        "varibles": [ "&none" ],
        "code": [ "</body>", "</html>" ]
    }
]
 </pre>
 ### .mweb Setup
   Your mweb file is very simple to set up, first create a new text file with the required info, then write your aspects, after that save it  as a .mweb
   <br> Required code<pre>
   [projName].json
   ^html
   ^head
   ^body
   *your aspects
   ^end
   </pre>
     <br> Example code<pre>
   [projName].json
exampleProj.json
^html
^head
^body
^header
^navbar
^footer
^end
   </pre>
 </pre>
 ### [NEW] Varibles
  Recently I added varible support, this way mweb is more dynamic, eg. you can have a html div block for upside down text or somthing, insead of having to add multiple of the same aspec with differnt text content, you now just have to add a varible. To use this you just have to add a varible name into the varible section, and add the varible into the aspect code array:
   <br> Example Aspect code<pre>
  {
        "aspect": "^header",
        "varibles": [ "&page-title","&description"],    *two varibles, in the .mweb you have to follow the ording, eg. ^header&Home Page&This is the page description
        "code": [
            "< div",
            "class='header'>",
            "< h1>",
            "&page-title", *varible must be in a new array position
            "< /h1>",
            "< p>",
            "&description",
            < /p>",
            "< /div>"
        ]
    },
   </pre>
     <br>  Example .mweb code<pre>
exampleProj.json
^html
^head
^body
^header&Page Title&Page Description
^end
   </pre>  
 ### Running mweb
 To run your page just double click the .mweb and the rest shoudld work it self <br>
 To run your project with commands open a cmd window and type [path/to/.mweb] -[command] (list of commands can be shown via command -help)<br>
 To export your .mweb as specified file then run with the command -export
