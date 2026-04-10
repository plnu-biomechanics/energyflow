# 🔩 Sample code to ingest energy flow data into your working environment

```
import urllib.request
import zipfile
import os

# --------------------------------------------------
# Configuration (do NOT edit below)
# These lines create a directory for this lab in your
# Colab working directory.
# --------------------------------------------------
zip_dir = "kin6050/data"
os.makedirs(zip_dir, exist_ok=True)

zip_filename = "SPM_EF_HS_College.zip"

url = (
 "https://raw.githubusercontent.com/"
 "plnu-biomechanics/energyflow/main/"
 f"data/{zip_filename}"
)

zip_path = os.path.join(zip_dir, zip_filename)

# --------------------------------------------------
# Download zip file
# --------------------------------------------------
urllib.request.urlretrieve(url, zip_path)

# --------------------------------------------------
# Extract contents from the zipped file
# --------------------------------------------------
with zipfile.ZipFile(zip_path, "r") as zip_ref:
   zip_ref.extractall(zip_dir)

print("Extracted files in working directory:")
print(os.listdir(zip_dir))
```
