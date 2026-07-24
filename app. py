import pytesseract
import pandas as pd
from pdf2image import convert_from_path

# 1. PDF को इमेजेस (Photos) में बदलें
images = convert_from_path("scanned_file.pdf")

# 2. पहली इमेज से OCR की मदद से टेक्स्ट निकालें
text = pytesseract.image_to_string(images[0])

# 3. टेक्स्ट की लाइनों को स्प्रेडशीट की रो में बदलें
rows = [line.split() for line in text.split("\n") if line.strip()]

# 4. Excel में सेव करें
df = pd.DataFrame(rows)
df.to_excel("scanned_data.xlsx", index=False, header=False)

print("स्कैन की हुई PDF का डेटा Excel में कन्वर्ट हो गया!")
