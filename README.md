# cizim2[hii_quick.py](https://github.com/user-attachments/files/26108593/hii_quick.py)
import os
from datetime import datetime, timedelta

# Repo klasöründe kal
os.chdir(os.getcwd())

# Hİİ grafiği: 'X' = commit atılacak kare
HII_pattern = [
    ['X','','X','',''],
    ['X','','X','',''],
    ['X','X','X','X','X'],
    ['X','','X','',''],
    ['X','','X','','']
]

# Başlangıç tarihi: kaç hafta önce başlasın
start_date = datetime.today() - timedelta(weeks=len(HII_pattern[0]))

# Commitleri oluştur
for col in range(len(HII_pattern[0])):
    for row in range(len(HII_pattern)):
        if HII_pattern[row][col] == 'X':
            date = start_date + timedelta(weeks=col, days=row)
            os.system(f'git commit --allow-empty -m "Hİİ" --date="{date.strftime("%Y-%m-%dT12:00:00")}"')

# Push
os.system('git push')

print("Hİİ grafiği hazır!")
