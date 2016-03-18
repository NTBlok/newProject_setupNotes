### New project setup notes

Create a top level directory and cd into it.

    mkdir ~/myproject
    cd ~/myproject

This directory will hold a directory for the git repo and a directory to store project related environmental variables to be sourced prior to working on this project.  
Next create these two directories here.

    mkdir mydjango_project
    mkdir mykeys

Also, in this directory start a virtual environment to work in.

    virtualenv venv

Then create a shell script inside the mykeys directory with environmental variables for this project.

    touch mykeys/env.sh

Inside mykeys/env.sh, add:

    export VIRTUAL_ENV=~/myproject/mydjango_project/venv
    export PATH="$VIRTUAL_ENV"/bin:"$PATH"

Source the mykeys/env.sh file and activate the virtual environment to start installing dependencies.

    source mykeys/env.sh
    source venv/bin/activate

Begin installing initial dependencies in virtual environment:

    pip install Django==1.9.2
    pip install markdown

Create a markdown readme file in the mydjango_project directory.  

    touch mydjango_project/README.md

To preview this markdown file from a remote server use the following 2-step process:  

1. Run the python markdown converter to a readme.html file in the top-level directory  

    `python -m markdown mydjango_project/README.md > readme.html`

2. Run the python simple HTTP server on a desired port (say, 8090) then point a local browser at the remote ip:8090/readme.html

    `python -m SimpleHTTPServer 8090`

Change directories into mydjango_project and initialize a new git repository

    cd mydjango_project
    git init

Add/edit favorite .gitignore
