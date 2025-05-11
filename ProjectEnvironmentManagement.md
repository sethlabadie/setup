## Project Folders

Here is how I set up my project folders.

In my home directory, I have a folder called "Dev," which contains all my projects.

Within the Dev folder, I have 00_Project_Template, which as the name implies, is a template that I copy to start a new project.

Next is 01_Bloat_Project, which contains a virtual environment with all sorts of of packages installed; I use this for quick coding and small projects, just to try stuff out.

For each new project, I increment the number and give it a name in Pascal Case.


00_Project_Template has the following folder structure:

02_Sample_Project<br>
├── 00_admin_(charter,scopingDocs)<br>
├── 01_documents_(reference,meetingNotes)<br>
├── 02_inputs # This is where raw data goes; I then copy it to 03_WIP to clean it and analyze<br>
├── 03_WIP # This is where I spend 95% of my time. It includes a subfolder with the coding project,<br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;plus all of the other work-in-progress files, such as draft PowerPoint slides or Excel WorkBooks.<br>
└── 04_outputs # Final results go here, such as final presentations or final spreadsheets

This structure works because it can be used for any project, such as a consulting project or a data analysis project which doesn't involve any code. In that case, 03_WIP would include the data analysis project, plus all of the other work-in-progress files, such as draft PowerPoint slides or Excel WorkBooks. 04_outputs would include the final results, such as final presentations or final spreadsheets. It also works for Data Science projects, since like consulting projects, there will be customer / manager guidance, documents, meeting notes, and other administrative files. The entire coding project (other than the administrative documents or the final output, which may be in Excel or PowerPoint) will be in the 03_WIP folder. The 02_inputs folder will contain the raw data, which will be copied to the 03_WIP folder for cleaning and analysis, although another option is to put the raw data used for a coding project as a subdirectory in 03_WIP. The 04_outputs folder will contain the final results, such as a PowerPoint presentation or an Excel spreadsheet.

For Data Science or coding projects, I generally use the following folder structure for 03_WIP (modified for the project).

02_Sample_Project<br>
├── 00_admin_(charter,scopingDocs)<br>
├── 01_documents_(reference,meetingNotes)<br>
├── 02_inputs<br>
└── 03_WIP<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── sample_project-py<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── .venv<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── src<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── tests<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── .envrc<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── .python-version<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── poetry.lock<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── pyproject.toml<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── README.md<br>
└── 04_outputs



## Setting Up a Virtual Environment

Copy the 00_Project_Template directory structure and rename it to your project name. Navigate to the 03_WIP folder.<br>

Create your Python project by issuing the ```poetry new test-py``` command (rename test-py to whatever your project name is). This creates a project directory with the following contents: test-py directory; tests directory; pyproject.toml; and README.md.<br>

```cd``` into the project folder and rename the second (nested) project folder to ```src```. Then open the pyproject.toml file and make any modifications you need, such as to the description field.<br>

Add some modules that you know you will need by issuing the ```poetry add numpy pandas requests``` command (edit for your needs). This will write these modules to the pyproject.toml file, create a poetry.lock file, create a virtual environment (.venv) directory, and install the modules.<br>

Issue the ```pyenv local 3.12``` command (substitute the version number for any other version of Python you might want). This creates a ```.python-version``` file.<br>

If you want to create a per-project isolated development environment, create a blank ```.envrc``` file. When you navigate to this directory, **direnv** will recognize it and load the environment variables for that project.<br>

Issue the ```git init``` command to start a git repository.

Your project is setup. If you navigate into the project directory, pyautoenv will automatically activate the virtual environment, and direnv will load the ```.envrc``` file. If you navigate away from the project folder, they will exit and unload.