# uniserve
UniServe - Web-based Service Exchange Platform for University Students

**Problem**
Students at UICT struggle to access essential campus services due to reliance on physical advertisements, word-of-mouth, and informal WhatsApp groups. These methods lack:
Verification – No way to confirm if a provider is legitimate
Organization – Services are scattered, not searchable
Accountability – No reviews or ratings to guide trust
Feedback mechanisms – No way to report poor service

As a result, students waste time and money, while talented students miss opportunities to monetize their skills.

**Solution**
UniServe is a web-based peer-to-peer platform that:
Allows students to post services they offer
Allows students to search and request services
Provides user verification through admin approval
Includes ratings and reviews for accountability
Has built-in messaging for direct communication
Tracks request status (pending → accepted → completed)

Setup Instructions (Local Server)
Note: Since my Render paid instance has expired, these instructions cover running UniServe entirely on your local machine using a local server.

Prerequisites
Before you begin, ensure you have the following installed on your computer:

Software	Version	Download Link
Python	3.8 or higher	python.org
Git (optional)	Latest	git-scm.com
VS Code or any text editor	Latest	code.visualstudio.com
Verify Python installation: Open Command Prompt/Terminal and type:

bash
python --version
or

bash
python3 --version
Step 1: Get the Project Files
You have two options:


Option A: If you have the project folder already
Skip to Step 2.

Option B: If you need to download/clone the project
bash
# Clone from GitHub (if hosted)
git clone https://github.com/yourusername/uniserve.git
cd uniserve

# OR if you have a ZIP file, extract it and navigate to the folder
cd path/to/uniserve
Step 2: Create a Virtual Environment
A virtual environment isolates project dependencies so they don't conflict with other Python projects.

On Windows:

bash
python -m venv venv
venv\Scripts\activate
On Mac/Linux:

bash
python3 -m venv venv
source venv/bin/activate
Your terminal should now show (venv) at the beginning of the prompt.

Step 3: Install Dependencies
Install all required Python packages using the requirements.txt file (if available).

bash
pip install -r requirements.txt
If requirements.txt is missing, install manually:

bash
pip install flask flask-sqlalchemy flask-bcrypt flask-login flask-wtf email-validator
Step 4: Configure the Database
UniServe uses SQLite, which requires no separate database server. The database file will be created automatically.

bash
# Open Python interactive shell
python
Then run:

python
from app import app, db
with app.app_context():
    db.create_all()
    print("Database created successfully!")
exit()
Alternatively, if you have a script:

bash
python init_db.py
This will create a file named instance/uniserve.db in your project folder.

Step 5: (Optional) Seed Sample Data
To test the platform with sample users and services:

bash
python seed_data.py
If this file doesn't exist, you can manually register users through the web interface.

Step 6: Run the Application
Start the Flask development server:

bash
python app.py
or

bash
flask run
Expected output:

text
 * Running on http://127.0.0.1:5000 (Press CTRL+C to quit)
Step 7: Access the Application
Open your web browser and go to:

http://127.0.0.1:5000 or http://localhost:5000

You should see the UniServe homepage.



