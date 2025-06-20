import os
from datetime import datetime
from github import Github

# ======= 設定 =======
GITHUB_TOKEN = os.getenv("GITHUB_TOKEN")
REPO_NAME = "bubucolic1111/bubucolic1111"
TOEIC_DATE = datetime(2025, 7, 27, 0, 0, 0)  # 設定考試日期

# ======= 初始化 =======
g = Github(GITHUB_TOKEN)
repo = g.get_repo(REPO_NAME)

# ======= 計算倒數時間 =======
now = datetime.utcnow()
diff = TOEIC_DATE - now

days = diff.days
hours = diff.seconds // 3600
minutes = (diff.seconds % 3600) // 60
seconds = diff.seconds % 60

countdown_str = f"🕒 **{days} 天 {hours} 小時 {minutes} 分鐘 {seconds} 秒**"

# ======= 產出 README 內容 =======
readme = f"""# 👋 bubucolic1111 正在努力準備 TOEIC！

---

## ✅ 倒數計時牆

距離 TOEIC 考試還有：  
{countdown_str}

---

## 🌍 家鄉推薦牆

（此區未啟用，未來可擴充）

---

## 📝 訪客簽到留言板

（此區未啟用，未來可擴充）
"""

# ======= 寫入 README.md =======
with open("README.md", "w", encoding="utf-8") as f:
    f.write(readme)
