To get pdf:
1. jupyter nbconvert --to html PythonPractise.ipynb
2. open PythonPractise.html in browser and take a printout

To get docs:
1. make sure you have installed pandoc in system (i did it manually)
2. jupyter nbconvert --to markdown PythonPractise.ipynb
3. pandoc PythonPractise.md -o PythonPractise.docx