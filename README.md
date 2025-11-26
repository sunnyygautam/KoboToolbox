# KoboToolbox
✅ How to Install KoboToolbox on Windows Using Docker Desktop
1. Install Prerequisites
✔ Step 1: Install WSL2 (Required for Docker Desktop)

Open PowerShell as Administrator and run:

wsl --install


Reboot your system when asked.

✔ Step 2: Install Docker Desktop for Windows

Download & install:
🔗 https://www.docker.com/products/docker-desktop/

During installation:

Enable WSL2 backend

Enable Use Docker Compose V2

Restart Docker after installation.

✅ 2. Download KoboToolbox (Docker Setup)

KoboToolbox self-hosted version is available here:
🔗 https://github.com/kobotoolbox/kobo-install

Method A (Recommended): Use kobo-install setup tool
3. Install KoboToolbox Using kobo-install
✔ Step 1: Clone the Repository

Open PowerShell or WSL terminal:

git clone https://github.com/kobotoolbox/kobo-install.git
cd kobo-install

✔ Step 2: Start the Setup Wizard
python3 run.py


If python3 doesn't work:

python run.py


This will ask configuration questions:

Question	Recommended Answer
Install single server or multi-server?	Single server
Do you want to use HTTPS/SSL now?	No (you can add later)
Public domain?	localhost or your LAN IP
Do you want to use Docker Compose?	Yes

After finishing, it generates a folder named:

.volatile/

✔ Step 3: Start KoboToolbox Containers

Run:

docker compose up -d


Or if using old Docker versions:

docker-compose up -d

🎉 4. Access KoboToolbox Web Interface

After containers start, open:

✔ KoboToolbox (KPI):
http://localhost:8000

✔ KoBoForm (Form Builder):
http://localhost:8000/#/forms

✔ KoBoToolbox API:
http://localhost:8000/api/v2/

✔ KoBo Assets (Enketo):
http://localhost:8080

To access KoboToolbox running on Docker Desktop (Windows) at:

URL: http://kf.kobo.local
User: super_admin
Password: 5j18RwKDLDJKGvMDe03E


you must fix local DNS resolution, because “*.local” domains do not resolve automatically on Windows.

Here is the correct way to access it 👇

✅ Step 1 — Add hosts entries in Windows

Open Notepad as Administrator

Go to File → Open

Open the file:

C:\Windows\System32\drivers\etc\hosts


Add these lines at the bottom:

127.0.0.1   kf.kobo.local
127.0.0.1   kc.kobo.local
127.0.0.1   ee.kobo.local

Save the file.
