# Maharashtra--Foods
from zipfile import ZipFile
from pathlib import Path

root=Path('/mnt/data/maharashtra-foods-website')
root.mkdir(exist_ok=True)
(root/'index.html').write_text("""<!doctype html><html><head><meta charset='utf-8'><meta name='viewport' content='width=device-width,initial-scale=1'><title>Maharashtra Foods</title><link rel='stylesheet' href='style.css'></head><body><header><h1>Maharashtra Foods</h1><p>Your Bakery Shop in Amrutnagar</p></header><main><h2>Welcome</h2><p>Bakery, Cakes, Namkeen, Sweets, Biscuits. All Chakote brand items available.</p><p>Hours: 9 AM–9 PM</p><p>WhatsApp: <a href='https://wa.me/918459805252'>8459805252</a></p><p>Call: <a href='tel:+918459805252'>8459805252</a> | <a href='tel:+918830073035'>8830073035</a></p></main></body></html>""")
(root/'style.css').write_text("body{font-family:Arial;margin:0;padding:2rem;background:#fff8f0}header{background:#b22222;color:#fff;padding:2rem;text-align:center}main{max-width:800px;margin:auto}")
zip_path='/mnt/data/Maharashtra_Foods_Website.zip'
with ZipFile(zip_path,'w') as z:
    for f in root.iterdir():
        z.write(f,f.name)
print(zip_path)

