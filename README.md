# lesson-4
oop lesson 4


✅ סיכום הנקודות העיקריות
1. הפרדת אחריות בין סוגי מתודות
🧍‍♂️ self (מתודות רגילות) – פועלות על מופע מסוים (כמו deposit, withdraw, is_rich).

🧑‍🏫 @classmethod – פועלות על המחלקה עצמה (cls), כמו get_bank_address.

⚙️ @staticmethod – לא תלויות במחלקה או במופע, לדוגמה highest_balance.

2. שימוש ב־Encapsulation (הסתרת מידע)
הגדרתי תכונות פרטיות עם __ כמו __owner, __balance, __bank_address כדי למנוע גישה ישירה.

סיפקתי propertyים ל־owner ול־balance לצורך גישה מבוקרת:

owner: קריאה בלבד.

balance: קריאה וכתיבה באמצעות @property ו־@balance.setter.

3. מימוש פעולות בסיסיות של חשבון בנק
deposit() – הוספת כסף לחשבון.

withdraw() – הורדת כסף.

is_rich() – בדיקת עושר לפי תנאי (> מיליון).

4. שימוש ב־Operator Overloading
✅ חיבור: __add__ תומך בחיבור חשבון לחשבון או למספר.

➖ חיסור: __sub__ תומך בחיסור בין חשבונות או ממספר.

🔁 השוואות: ==, !=, <, >, >=, <= הוגדרו לפי דרישה.

מאפשר תמיכה גם בהשוואה למספרים (800) או tuple (('Alice', 800)).

5. מתודות עזר לפיתוח ולנוחות
__repr__ – תיאור מפורט למפתחים.

__str__ – תיאור ידידותי להדפסה.

__len__ – מחזיר את היתרה כ־int מעוגל.

__getitem__ – מאפשר גישה כמו מילון/רשימה.

__iter__ – איטרציה על שם + יתרה.

6. פיצ'ר בונוס – הקפאת חשבון
freeze() – הופך את החשבון ללא פעיל על ידי איפוס בעל החשבון והיתרה.

💡 דגשים חשובים לקחת בחשבון
נושא	דגשים
OOP נכון	השתמשנו בהכל: property, classmethod, staticmethod, Overloading, __str__ וכו'.
בטיחות	שמרנו על פרטיות נתונים (__balance, __owner) באמצעות encapsulation.
קריאות קוד	חילקנו את הקוד לפי קטגוריות בצורה ברורה.
גמישות השוואה	תמיכה ב־== מול חשבון, מספר, tuple.
שימוש נכון בפונקציות מיוחדות	כל שיטה מיוחדת (__add__, __getitem__, וכו') נכתבה עם טיפול נכון בסוגי קלט שונים.






📋 טבלה מסכמת – פונקציות במחלקה BankAccount
✨ שם הפונקציה	🧠 סוג (Instance / Class / Static / Special)	📝 שימוש	🔗 תלות
__init__	Constructor (instance)	יצירת מופע עם שם ויתרה	self
owner	Getter (property)	גישה לקריאה בלבד לשם הבעלים	self
balance	Getter (property)	גישה לקריאה בלבד ליתרה	self
balance(value)	Setter (property)	הגדרת יתרה חדשה	self
deposit(amount)	Method (instance)	מפקיד כסף לחשבון	self
withdraw(amount)	Method (instance)	מושך כסף מהחשבון	self
is_rich()	Method (instance)	בודק אם יש מעל מיליון ש״ח	self
get_bank_address()	Method (class) @classmethod	מחזירה את כתובת הבנק	cls
highest_balance(a1,a2,a3)	Method (static) @staticmethod	מחזירה את היתרה הגבוהה ביותר	אף אחד
__add__(other)	Special Method (+ operator)	חיבור חשבונות או הוספת מספר	self
__sub__(other)	Special Method (- operator)	חיסור בין חשבונות או ממספר	self
__eq__(other)	Special Method (== operator)	השוואת שם ויתרה	self
__ne__(other)	Special Method (!= operator)	שלילה של __eq__	self
__gt__(other)	Special Method (> operator)	השוואת יתרה בלבד	self
__ge__(other)	Special Method (>= operator)	השוואת יתרה בלבד	self
__lt__(other)	Special Method (< operator)	השוואת יתרה בלבד	self
__le__(other)	Special Method (<= operator)	השוואת יתרה בלבד	self
__repr__()	Special Method (developer view)	ייצוג טכני למפתחים	self
__str__()	Special Method (user view)	הדפסה ידידותית לחשבון	self
__len__()	Special Method (len(account))	מחזיר יתרה מעוגלת כ-int	self
__getitem__(key)	Special Method (account[key])	גישה לפי 'owner' / 'balance' / 0 / 1	self
__iter__()	Special Method (for x in account)	איטרציה על שם ויתרה	self
freeze()	Method (instance)	מקפיא חשבון: שם = FROZEN, יתרה = 0	self

🧠 טיפי למידה:
השתמש תמיד ב־@property כשאתה רוצה שליטה על גישה לתכונות.

@staticmethod מיועדת לכלי עזר – לא צריך self.

@classmethod כשצריך לגשת או לשנות משתני מחלקה.

Overloading של פעולות (__add__, __eq__, וכו') נותן למחלקה שלך אינטראקציה טבעית עם פייתון.

