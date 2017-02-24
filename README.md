It is a guide (very practical), especially suited for users who want to create <strong>an executable (.exe)<br> 
file</strong> of a <strong>project created with Node.js</strong>

- <strong>STEP 1</strong><br>
You need to download some software:<br>
1.1) <a href="http://www.battoexeconverter.com/">Advanced BAT to EXE converter v4.07</a> (Not tested on other versions)<br>
1.2) <a href="http://gnuwin32.sourceforge.net/downlinks/unzip-bin-zip.php/">Unzip.exe</a> (Only binaries)<br>
1.3) <a href="https://nodejs.org/dist/v6.9.5/win-x86/node.exe">Node.exe 6.5.9 32bit</a> or <a href="https://nodejs.org/dist/v6.9.5/win-x64/node.exe">Node.exe 6.5.9  64bit</a> (Only binaries) (Not tested on other versions)<br>

- <strong>STEP 2</strong><br>
2.1) After downloading the files needed to create the executable. We install Advanced BAT to EXE Converter v4.07.<br>
2.2) Now move <strong>"Unzip.exe"</strong> in the Node.js project folder.<br>
2.3) Now move <strong>"Node.exe"</strong> in the Node.js project folder<br>

- <strong>STEP 3</strong><br> 
3.1)After you have successfully moved the binaries in the Node.js project folder,<br> 
you have to compress, in a <strong>".zip"</strong> file, <strong>one by one all</strong> the folders that are present<br>
in the <strong>project folder</strong>.<br>
<strong>Example: </strong>node_modules.zip, app.zip, resources.zip, etc.<br>
<br>
3.2) Now we move on to Advanced BAT to EXE converter.<br> 
In the homepage of the program we have to insert some codes<br>
Erases whatever is written and enter the following code(one below the other):<br>
<br>
<strong>CD %MYFILES%/</strong> (%MYFILES% is the variable given to the location of embedded files. More on that in a sec)<br>
<br>
<strong>unzip.exe node_modules.zip</strong> (This code allows "unzip.exe" to extract the file (in this case node_modules.zip)<br>
in the folder specified by the above variable.)<br>
<br>
<strong>unzip.exe app.zip</strong> (This code allows "unzip.exe" to extract the files (in this case app.zip)<br> 
in the folder specified by the previous variable.)<br>
<br>
<i>These folder names are just one example. You must tell the program all the archives (.zip) that are present in the root folder of your project.</i><br>
<br>
<strong>node TestApp.js</strong> (Finally we have to tell the program the name of the file that will run from Node.exe (In this case "TestApp.js")<br>
<br>
3.3) Now we click on "<strong>File</strong>" at the top left and select the "<strong>Build EXE ...</strong>"<br>

- <strong>STEP 4</strong><br>
4.1) Now for the "<strong>Embed Files</strong>" tab.<br>
4.2) Click on "+" to the right. And <strong>select all files</strong> in the project folder. <strong>Do not forget to select "Unzip.exe" and "Node.exe"</strong>.<br>
<br>
<i>I remind you that "Advanced BAT to EXE convertion" can not select the files that are contained in subfolders.<br> 
(Which is why we have decided to close each folder in a file in ".zip" format).<br>
In this way, by storing each folder in a ".zip" we can manage all the files in the sub-folders of the project "Node.js".<br>
Then thanks to the command "unzip.exe", the program decompresses all the "archives" and allows our project to be run by the ".exe" file</i><br>
<br>
4.3) After you select all the items in our project folder written in "Node.js", we create the executable by clicking on "<strong>Build EXE</strong>" on the bottom right.<br>
4.4) No we just have to give a name to our executable and you're done.
<br>
<br>
- <strong>Optional</strong> 
complete structure of the example used in this guide.<br>
| Project Folder<br>
|__ /App (folder)<br> 
|______/Various subfolders and files (subfolder of App folder)<br>
|__ /Node_module (folder) <br>
|_______/Various subfolders and files (subfolder of Node_modules folder)<br>
|__package.json<br>
|__TestApp.js<br>
<br>
Now all folders within them have other folders (then sub-folders) will be stored in a ".zip"<br>
<br>
- <strong>Full command structure</strong><br>
CD %MYFILES%/<br>
unzip.exe app.zip<br>
unzip.exe Node_modules.zip<br>
node AppTest.js<br>
