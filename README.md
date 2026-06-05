from pathlib import Path
import zipfile

html = r"""<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SIXTYNINE EXCLUSIVE</title>
<style>
body{font-family:Arial,sans-serif;margin:0;background:#fff;color:#000}
header{background:#000;color:#fff;text-align:center;padding:40px 20px}
nav{display:flex;justify-content:center;gap:20px;background:#111;padding:12px}
nav a{color:#fff;text-decoration:none}
section{padding:40px 20px;max-width:1000px;margin:auto}
.card{border:1px solid #ddd;padding:20px;margin:10px 0}
footer{background:#000;color:#fff;padding:20px;text-align:center}
</style>
</head>
<body>
<header>
<h1>SIXTYNINE</h1>
<h3>EXCLUSIVE</h3>
</header>

<nav>
<a href="#home">หน้าหลัก</a>
<a href="#products">สินค้า</a>
<a href="#settings">การตั้งค่า</a>
<a href="#contact">ติดต่อ</a>
</nav>

<section id="home">
<h2>ยินดีต้อนรับสู่ SIXTYNINE EXCLUSIVE</h2>
<p>Streetwear for Dream Chasers</p>
</section>

<section id="products">
<h2>สินค้า</h2>
<div class="card">เพิ่มสินค้าเสื้อผ้าของคุณได้ที่นี่</div>
<div class="card">หมวดหมู่สินค้า</div>
</section>

<section id="settings">
<h2>การตั้งค่า</h2>
<p>พื้นที่สำหรับเพิ่มการตั้งค่าร้านค้า โปรโมชั่น และข้อมูลอื่น ๆ</p>
</section>

<section id="contact">
<h2>ติดต่อเรา</h2>
<p>โทร: 095-284-3505</p>
<p>อีเมล: SIXTYNINEEXCLUSIVE@gmail.com</p>
<p>Facebook: SIXTYNINE</p>
<p>Instagram: SIXTYNINE</p>
<p>TikTok: SIXTYNINE</p>
</section>

<footer>
<p>© SIXTYNINE EXCLUSIVE</p>
</footer>
</body>
</html>"""

path = "/mnt/data/SIXTYNINE_EXCLUSIVE.html"
Path(path).write_text(html, encoding="utf-8")

zip_path = "/mnt/data/SIXTYNINE_EXCLUSIVE_Website.zip"
with zipfile.ZipFile(zip_path, "w") as z:
    z.write(path, arcname="index.html")

print({"html": path, "zip": zip_path})
