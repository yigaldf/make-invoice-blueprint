# חיפוש חשבוניות מהשבוע האחרון – Make Blueprint

אוטומציה ב-[Make](https://www.make.com) שמחפשת חשבוניות וקבלות ב-Gmail מ-7 הימים האחרונים, שומרת את הקבצים ב-Google Drive ומתעדת כל חשבונית בשורה ב-Google Sheets.

הקובץ: [`invoice-search-last-week.blueprint.json`](invoice-search-last-week.blueprint.json)

## הזרימה

1. **Gmail – Search emails**: מיילים מהשבוע האחרון עם קובץ מצורף ומילים כמו חשבונית / קבלה / invoice / receipt, בלי מיילים שכבר טופלו.
2. **Make AI Toolkit – Extract**: מודל AI קורא את הנושא וגוף המייל, מחליט אם זו חשבונית ומחלץ ספק, סכום, מטבע, מספר ותאריך. אם ה-AI נכשל על מייל, הוא מדולג (Skip).
3. **Gmail – List attachments**: רק למיילים שה-AI אישר כחשבונית.
4. **Google Drive – Upload a File**: שומר קבצי PDF ותמונות לתיקיית "חשבוניות".
5. **Google Sheets – Add a Row**: שורה לכל חשבונית עם הנתונים וקישור לקובץ.
6. **Gmail – Update labels**: מוסיף תווית `invoices-saved` כדי שהמייל לא יעובד שוב.

ההפעלה ידנית (Run once).

## ייבוא

ב-Make: יוצרים סצנריו חדש ← תפריט ⋯ ← **Import Blueprint** ← בוחרים את קובץ ה-JSON.
אחרי הייבוא צריך לבחור חיבורים משלכם ל-Gmail, Google Drive, Google Sheets ו-Make AI, ולעדכן את תיקיית ה-Drive, הגיליון והתווית לאלה שבחשבון שלכם.
