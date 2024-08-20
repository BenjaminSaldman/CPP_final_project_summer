# פרויקט גמר - מונופול
בתור פרויקט הגמר שלכם בקורס אתם תממשו גרסה של המשחק המוכר והידוע "מונופול".
מונופול הוא משחק לוח המכיל 2-8 שחקנים ומבוסס על עולם העסקים.
בפרויקט הזה אתם תממשו גרסה של המשחק המיועדת ל-2 עד 8 שחקנים המשחקים דרך אותו המחשב.
## חוקי המשחק
המשחק מורכב מלוח המכיל 40 משבצות המקיפות אותו, כל משבצת יכולה לייצג רחוב, קווי רכבת, משבצות מיוחדות ועוד. בהמשך נפרט על סוגי המשבצות השונים.

### משבצות הלוח
כידוע, הלוח מחולק ל-40 משבצות שונות כאשר בכל משבצת השחקן יכול לבצע פעולות שונות. עליכם לבנות לוח דינאמי המאפשר הוספה של משבצות נוספות למשחק. הפורמט המבוקש הוא לפי הלוח הבא: https://shorturl.at/T3HfV
#### רחובות
משבצת הרחוב שייכת לקבוצת צבע כלשהי מתוך 8 קבוצות צבע אפשריות. לכל רחוב יש שם, מחיר, עלות שכירות, מחיר בית ומחיר שכירות עם בית. שחקן יכול לבנות בית ברחוב כלשהו רק אם הוא מחזיק בכל הרחובות השייכים לאותה קבוצת הצבע. כאשר שחקן נוחת ברחוב השייך לשחקן אחר הוא מחוייב לשלם לו שכירות לפי מה שבנוי באותו הרחוב - אם הרחוב ריק (כלומר ללא בית) השחקן ישלם את מחיר השכירות של אותו הרחוב אבל אם הרחוב מכיל בית השחקן ישלם את השכירות לפי המחיר עם בית. סוגי הצבעים, השמות של הרחובות והמחירים נתונים לשיקול דעתכם.
##### בניית בתים
כזכור, שחקן יכול לבנות בית ברחוב מסוים רק אם מחזיק בכל הרחובות השייכים לאותה קבוצת צבע. ניתן לרכוש עד 4 בתים לכל רחוב ולאחר מכן גם מלון לפי החוקים הבאים:
* כדי לקנות בית נוסף, על השחקן לבנות את אותו המספר של בתים בשאר קבוצות הצבע (כלומר, נניח שיש לי 2 רחובות השייכים לאותה קבוצת צבע ובאחד בניתי בית ובשני לא. לא אפשרי לבנות בית נוסף אלא אם בניתי בית ברחוב של נבנה בו לפני).
* ניתן לבנות בית נוסף במחיר של בית רגיל (כלומר אם עלות בנייה של בית היא 100 שקלים, אז עלות כל בית נוסף גם תהיה 100 שקלים).
* ניתן לבנות מלון רק אחרי שנבנו 4 בתים באותו הרחוב. מחיר המלון הוא מחירם של 4 בתים + 100 שקלים.
* דמי השכירות גדלים פי 2 ככל שמוסיפים יותר בתים, כלומר אם דמי השכירות עבור בית אחד הם 50 שקלים, אזי דמי השכירות עבור 2 בתים יהיו 100 שקלים.
#### רכבות
במשחק יש 4 רחובות, רכבת אחת בכל צד של הלוח. העלות של כל רכבת היא 200 שקלים. כאשר שחקן נוחת ברכבת של שחקן אחר הוא ישלם לו מס לפי מספר הרכבות של השחקן אצלו נחתו:
* רכבת אחת - 50 שקלים
* 2 רכבות - 100 שקלים
* 3 רכבות - 150 שקלים
* 4 רכבות - 200 שקלים
#### משבצות מיוחדות
הלוח מכיל משבצות מיוחדות מסוגים שונים.

* משבצת הפתעה - אם השחקן נוחת על המשבצת הזאת הוא מקבל איזושהי "הפתעה", למשל כרטיס יציאה מהכלא או זיכוי של כסף לחשבון. על ההפתעות להיות דינאמיות - כלומר כל הזמן ניתן לייצר הפתעות נוספות. לרשותכם דוגמה להפתעות היכולות להופיע במשחק בקובץ ```monopoly_chance_cards.txt```.
* משבצת "חנייה חופשית" - אם השחקן נוחת במשבצת הזאת הוא מסיים את התור ומעביר אותו לשחקן הבא.
* משבצות מס - אם השחקן נוחת במשבצות מהסוג הזה הוא משלם מס על סך 100 שקלים.
* משבצת "לך לכלא" - אם השחקן נוחת על המשבצת הזאת הוא נכנס לכלא ומשחק לפי הכללים של המשבצת הזאת.
* חברת החשמל וחברת המים - הלוח מכיל 2 משבצות עבור חברת המים וחברת החשמל. עלות על חברה היא 150 שקלים ואם שחקן נוחת במשבצת כזאת שהיא בבעלותו של שחקן אחר, עליו לשלם לאותו שחקן את סכום ההטלה כפול עשר.
#### הכלא
שחקן יכול להיכנס לכלא רק אם נחת על המשבצת "לך לכלא" או קיבל 3 פעמים ברצף "דאבל" בהטלות של הקוביה.
השחקן נמצא בכלא למשך 3 תורים שבמהלכם יכול לנסות לצאת מהכלא בדרכים הבאים:
* להשתמש בקלף יציאה מהכלא (שמקבלים מתיבת ההפתעה).
* לשלם קנס של 50 שקלים.
* להטיל את הקוביות ולקבל "דאבל".

אם עברו 3 תורים והשחקן לא הצליח לצאת מהכלא, עליו לשלם מס של 50 שקלים.

### מהלך המשחק
כל השחקנים מתחילים במשבצת ההתחלה עם 1,500 שקלים ובכל סיבוב מטילים 2 קוביות ומתקדמים על הלוח לפי תוצאת ההטלה ולפי הכללים הבאים:
כל שחקן מתחיל את המשחק עם 1500 שקלים ובתורו מטיל 2 קוביות ומתקדם על הלוח לפי תוצאת ההטלה ולפי החוקים הבאים:
* אם השחקן נחת ברחוב פנוי, הוא יכול לרכוש את אותו הרחוב.
* אם השחקן עבר את משבצת ההתחלה, הוא מקבל 200 שקלים לחשבון שלו.
* אם השחקן נחת במשבצת מיוחדת הוא פועל לפי החוקים של אותה המשבצת (למשל אם נחת במשבצת של תשלום מס השחקן צריך לשלם מס מהחשבון).
* אם תוצאת ההטלה היא "דאבל" השחקן מקבל תור נוסף למשחק. אם הוא קיבל 3 פעמים ברציפות "דאבל" הוא נכנס לכלא לפי החוקים של "כנס לכלא".
* אם השחקן נחת בנכס של שחקן אחר עליו לשלם לו שכירות/מס לפי החוקים של המשבצות.
* אם שחקן לא יכול להרשות לעצמו לשלם מס נוסף הוא "פושט רגל" ויוצא מהמשחק. אם השחקן פושט רגל בגלל חוב לשחקן כלשהו, כל הנכסים של אותו השחקן (כולל הכסף) עוברים לשחקן שהוא הבעלים של החוב. אם החוב הוא לבנק, הבעלות על הרחובות נמחקת.

אם השחקן נחת בכל משבצת שהיא לא "לך לכלא" או "חניה חופשית" השחקן יכול לבנות בתים בנכסים שלו לפי חוקי המשחק.

### ניצחון במשחק
שחקן יכול לנצח במשחק רק אם אחד משני הדברים קורים:
* כל שאר השחקנים פשטו את הרגל.
* בבעלות השחקן 4000 שקלים.

## מה עליכם לממש
עליכם לממש את הגרסה של המשחק שתתמוך עד 4 שחקנים. חשבו כיצד לחלק את הקוד והמחלקות כך שיתאימו לחוקי המשחק.

כמו כן, עליכם לממש ממשק גרפי המדגים את המשחק, עליכם להדפיס את לוח המשחק והשחקנים על הלוח וליצור ממשק המאפשר לכל השחקנים לשחק בצורה מובנת (כלומר, כל שחקן יכול לראות את המשבצות הפנויות/תפוסות ואת הדברים שבבעלותו).

עליכם גם לכתוב טסטים מקיפים לקוד שכתבתם וגם להוסיף README מפורט.

לרשותכם כמה חומרי עזר:
* לקריאה נוספת על חוקי המשחק והלוח: https://en.wikipedia.org/wiki/Monopoly_(game) 
* מדריך ל-GUI בשם QT  https://wiki.qt.io/Qt_for_Beginners
* מדריך ל-GUI בשם SFML https://www.sfml-dev.org/tutorials/2.6/

אנחנו מדגישים שאתם יכולים להשתמש באיזו ספרייה שאתם רוצים כדי לממש את הממשק הגרפי.

שימו לב שהגשת הפרויקט היא אישית. מותר להתייעץ, לקבל עזרה, ולהשתמש באינטרנט אבל יש לדווח בכתב על כל עזרה שקיבלתם, בהתאם לתקנון היושר של המחלקה - https://www.ariel.ac.il/wp/cs/wp-content/uploads/sites/88/2020/08/Guidelines-for-Academic-Integrity.pdf.

בהצלחה!
