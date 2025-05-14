# Tech-Titan-Study-Helper
A website that uses AI to generate flash cards from a PDF uploaded by the user, created by Marcus Herman and Emmanuel Obeng for a semester long project at Towson University.

The website runs locally on a node.js server; in order to run the server, there are some dependancies that must be installed.

First install node.js via the provided link.
Install Node https://nodejs.org/

Once node.js is installed, open up command prompt and run the following command. If you are using PowerShell, ensure it is running as administrator.
npm install express mongoose multer multer-gridfs-storage

The AI used for the generation of flashcards is Chat GPT, using its API. The website uses a flask server to monitor a button on the flashcards page of the website. Once this button is pressed, it will excecute a python scrpit that will use tesseract OCR to convert the contents of the PDF to a string, then it will feed that string and a prompt to Chat GPT, and finally the respose is separated into individual flash cards. To update the page, the script will then use a template of the flashcards page to insert the flashcards, then it will replace the original flashcards page.

The dependencies for this script will be explaned below.

First ensure python is installed. The script was coded using python 3.13.3. Use the following link if python needs to be installed.
https://www.python.org/downloads/

To check if it is installed properly, open command prompt and run the following command.
python --version

Next, install pip. Pip is an installer that will be used to install the necessary libraries the script requires. Open command prompt and run the following command.
python -m ensurepip --upgrade

To check if it is installed properly, run the following command.
pip --version

Finally, the necessary libraries can be installed. To install everything, run the following commands.
pip install Flask
pip install flask-cors
pip install pytesseract
pip install openai
pip install pillow
pip install fitz
pip install beautifulsoup4

Now the server is ready to run. To start, download the three zip files in the repository and extract them onto your desktop.

Open python script named "backend_with_html_output.py", there are three paths that must be changed based on where the files are on your computer.

![image](https://github.com/user-attachments/assets/0a98d94a-6a70-407f-9cd8-763aa1812ba7)

Change these based on your file path, for example "C:/Users/mherm/Desktop/TTSH-main" is my path. There is also an "API_KEY" variable, I am unable to upload an API key from my personal account since it is not a buisness account. If you want the website to run on your personal computer, you must go to the following link, then click "create new secret key" and paste that key into the "API_KEY" varriable in the python script. It will only work if there are credits attached to your account. The least you can spend is five dollars.
https://platform.openai.com/api-keys

Once the paths are set, the servers are ready to run.

Open a command prompt window, navigate to "TTSH-main" using the "cd" command, then run the following command.
python backend_with_html_output.py

Next, open a separate command prompt window and navigate to "TTSH-backend", then run the following command.
node server.js

Now that both servers are running, open a browser window and paste the following link into the search bar.
http://localhost:3000/TTSH%20Homepage.html

Using the Upload page, upload one of the sample PDFs, then navigate to the flashcards page. Using the drop down menu, you can select the uploaded PDF and then click the "Generate Flashcards" button. It will take around a minute to generate. When finished, a new page will apear with flashcards.

Here is a video demonstrating the functionality of the website.

https://github.com/user-attachments/assets/da0b5fc1-1472-4003-aea7-3b4e40cbb9a4
