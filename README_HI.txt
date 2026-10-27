TUITIONAPP — फ्री शुरुआती प्रोटोटाइप

क्या काम करता है:
- छात्र जोड़ना/हटाना और WhatsApp नंबर सेव करना
- फीस रिकॉर्ड, due date, Paid/Pending/Late स्टेटस
- Attendance में P/A लगाना
- टेस्ट अंक और प्रतिशत
- Parent View सारांश
- WhatsApp संदेश तैयार करके WhatsApp खोलना (Send आपको दबाना है)
- JSON backup export

महत्वपूर्ण सीमाएँ:
1. डेटा केवल उसी browser/device के localStorage में है। Browser data clear करने पर डेटा मिट सकता है; Export Backup नियमित लें।
2. अभी secure login, cloud database, कई डिवाइस पर sync, वास्तविक UPI payment verification, automatic scheduled reminders और अलग parent login शामिल नहीं हैं। इसे वास्तविक विद्यार्थियों के संवेदनशील डेटा के लिए production app न मानें।
3. Paid बटन तभी दबाएँ जब भुगतान वास्तव में प्राप्त और सत्यापित हो गया हो। WhatsApp message में receipt text है, यह payment gateway receipt नहीं है।

सबसे आसान टेस्ट:
1. ZIP extract करें।
2. index.html को browser में खोलें। कुछ browsers में file:// पर सभी सुविधाएँ सीमित हो सकती हैं।
3. Website/PWA की तरह इस्तेमाल करने के लिए files को free static hosting (जैसे GitHub Pages) पर डालें। HTTPS hosting से Android Chrome में Add to Home screen विकल्प मिल सकता है।
4. Android Chrome में hosted website खोलें → menu ⋮ → Add to Home screen / Install app.

Termux में local server:
  pkg update
  pkg install python
  cd /path/to/tuitionapp
  python -m http.server 8080
फिर उसी फोन के browser में http://127.0.0.1:8080 खोलें। यह केवल उसी फोन पर टेस्ट के लिए है; इंटरनेट पर प्रकाशित website नहीं है।

अगला चरण production build होगा: Firebase Authentication + Firestore security rules, owner/parent roles, server-side verified payment integration, और opt-in WhatsApp templates. इन्हें जोड़ने से पहले वास्तविक डेटा/पेमेंट के लिए सुरक्षा समीक्षा जरूरी है।
