STUDENT REPORT CARD GENERATOR - VERCEL VERSION

Project structure:
  main.py                 Flask backend (Vercel detects this automatically)
  requirements.txt        Python dependencies
  public/index.html       Original HTML, unchanged
  public/style.css        Original CSS, unchanged

LOCAL TESTING
1. Install Python 3.10 or newer.
2. In the project folder run:
     pip install -r requirements.txt
3. Run:
     python main.py
4. Open http://127.0.0.1:5000

VERCEL DEPLOYMENT
1. Upload the project files/folders to the ROOT of your GitHub repository.
2. Import that repository in Vercel and deploy. The current Vercel Python runtime detects
   the Flask app exported as `app` in main.py; no custom start command is required.
3. For student records to persist reliably, create a PostgreSQL database (for example,
   Neon) and add its connection string in Vercel:
     Project Settings > Environment Variables
     Name: DATABASE_URL
     Value: your PostgreSQL connection string
   Redeploy after adding the variable.

IMPORTANT DATABASE NOTE
SQLite is used automatically for local testing. If deployed to Vercel without DATABASE_URL,
this version uses /tmp/students.db only as a temporary fallback. Vercel's function filesystem
is temporary and may be recreated, so student records are NOT guaranteed to persist in that
mode. Configure DATABASE_URL to a managed PostgreSQL database before using this for real
student records.

The original HTML and CSS were copied byte-for-byte into public/. Their design and styling
were not edited.
