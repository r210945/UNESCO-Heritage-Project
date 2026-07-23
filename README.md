# 1. Clone the repository
git clone https://github.com/<org>/heritage-treasures.git
cd heritage-treasures

# 2. Install Python dependencies
pip install -r requirements.txt --break-system-packages

# 3. Clean the raw dataset (creates the cleaned CSV used by Tableau)
python scripts/clean_data.py
