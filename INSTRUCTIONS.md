# CJR Electronics Premium E-Commerce blogger Theme
## Installation and Setup Guide (ස්ථාපන සහ සැකසුම් මාර්ගෝපදේශය)

මෙමඟින් ඔබට [blogger_theme.xml](file:///f:/nfs%20coppy/cjr%20wabsits/blogger_theme.xml) කේතය (code) සාර්ථකව Google Blogger වෙත ඇතුළත් කර, භාණ්ඩ (products) සහ ගෙවීම් ක්‍රමවේද (payments) සකසා ගන්නා ආකාරය පියවරෙන් පියවර පැහැදිලි කර ඇත.

---

### පියවර 1: Blogger Theme එක ඇතුළත් කිරීම (Installing the Theme)
1. මෙම ෆෝල්ඩරයේ ඇති **`blogger_theme.xml`** ගොනුව ඕපන් කර එහි ඇති සම්පූර්ණ කේතය (Ctrl+A සහ Ctrl+C මඟින්) **Copy** කරගන්න.
2. ඔබේ **Blogger Dashboard** (blogger.com) වෙත පිවිසෙන්න.
3. වම්පස ඇති මෙනුවෙන් **Theme** ක්ලික් කරන්න.
4. **Customize** බටන් එක අසල ඇති කුඩා ඊතලය (Dropdown arrow) ක්ලික් කර **Edit HTML** තෝරන්න.
5. එහි ඇති සියලුම පැරණි කේතයන් මකා දමා (Delete), ඔබ Copy කරගත් නව කේතය එතැනට **Paste** කරන්න.
6. ඉහළ දකුණු කෙළවරේ ඇති **Save (Floppy Disk)** අයිකනය ක්ලික් කර සේව් කරන්න.

---

### පියවර 2: වෙළඳසැල් සැකසුම් සකස් කිරීම (Configuring Shop Settings)
වෙබ් අඩවියේ ඇති කේතය (HTML Edit) තුළ ඉහළින්ම ඇති **JavaScript configuration block** එක මඟින් පහසුවෙන්ම ඔබේ WhatsApp සහ PayPal විස්තර වෙනස් කළ හැක:

`blogger_theme.xml` ගොනුවේ **රේඛා (lines) 940-955** අතර හෝ `STORE_CONFIG` ලෙස සෙවුම් කර පහත කොටස සොයාගෙන වෙනස් කරන්න:

```javascript
const STORE_CONFIG = {
  whatsappNumber: "94771234567",       // ඔබේ WhatsApp අංකය (ලංකාවේ අංකයට 94 යොදා 0 නැතුව ලියන්න)
  paypalEmail: "paypal-seller@cjr.com", // ඔබේ PayPal Email ලිපිනය
  currency: "LKR",                      // පෙන්විය යුතු මුදල් වර්ගය (LKR / USD)
  paypalConversionRate: 0.0031,         // LKR සිට USD වලට පරිවර්තනය වන අනුපාතය
  paypalCurrencyCode: "USD",            // PayPal ගනුදෙනු සඳහා Currency එක
  storeLocationUrl: "https://maps.google.com/?q=CJR+Electronics+Private+Limited", // Google Maps Link එක (Store Location)
  storeName: "CJR Electronics Private Limited",
  designerName: "Isuru Sithumina"
};
```

---

### පියවර 3: භාණ්ඩ ඇතුළත් කිරීම (Adding Products)
ඔබට ක්‍රම 2කට භාණ්ඩ ඇතුළත් කළ හැක:

#### ක්‍රමය A: Blogger Posts හරහා (Highly Recommended - වඩාත්ම නිර්දේශිත ක්‍රමය)
මෙය ඉතාමත් පහසු වන අතර, පාරිභෝගිකයාට වෙන වෙනම භාණ්ඩවල විස්තර පිටුවලට (detail pages) යාමට ද හැකියාව ලැබෙන Daraz-style ක්‍රමයයි.

1. **New Post** ක්ලික් කරන්න.
2. **Post Title:** භාණ්ඩයේ නම ලියන්න (උදා: *Arduino Uno R3 Core Board*).
3. **Labels (Categories):** දකුණු පස ඇති Labels තීරුවේ අදාළ Category එක ලියන්න (උදා: *Arduino Items*). 
   *(මතක තබා ගන්න: මෙනු බාර් එකේ ඇති Category නමටම සමාන විය යුතුය).*
4. **Post Body:** 
   - පළමුවෙන්ම භාණ්ඩයේ පින්තූරය ඇතුළත් කරන්න (Insert Image).
   - ඊට පසු මිල සඳහන් කරන්න. **මිල ලියන ආකාරය:** `LKR 1850` හෝ `Price: 1850` ලෙස සරලව ලියන්න. (අපගේ JS engine එක මඟින් මෙම මිල ස්වයංක්‍රීයව හඳුනාගෙන, ලස්සන price tag එකක් සාදා, Cart එකට එකතු කරයි).
   - ඔබට එම භාණ්ඩයට අදාළව PayPal direct link එකක් ඇත්නම්, එයද Post එක තුළට ලින්ක් එකක් (hyperlink) ලෙස ඇතුළත් කරන්න.
   - ඉන්පසු භාණ්ඩයේ විස්තරය (description) සාමාන්‍ය පරිදි ලියන්න.

---

#### ක්‍රමය B: Blogger Layout එක මඟින් (Adding via Layout Widgets)
ඔබට coding දැනුමක් නොමැතිව Blogger Layout එකෙන් product එකක් add කර මිල සහ link එක වෙනස් කරගැනීමට අවශ්‍ය නම්:

1. Blogger Dashboard හි **Layout** වෙත යන්න.
2. **`layout-products-section`** තීරුවේ ඇති **Add a Gadget** ක්ලික් කර **HTML/JavaScript** තෝරන්න.
3. **Title:** භාණ්ඩයේ නම සහ මිල සඳහන් කරන්න. (උදා: *Arduino Uno - 1850 LKR*).
4. **Content:** පහත ආකාරයට පින්තූරයේ ලින්ක් එක, විස්තරය සහ PayPal ලින්ක් එක ඇතුළත් කරන්න:
   ```html
   <!-- පින්තූරයේ ලින්ක් එක -->
   src="https://example.com/image.jpg"
   
   <!-- PayPal Link එක (Buy Now සඳහා) -->
   href="https://www.paypal.com/ncp/payment/MOCK_ID"
   
   <!-- විස්තරය -->
   මෙම උපාංගය මඟින් ව්‍යාපෘති පහසුවෙන් නිර්මාණය කළ හැකිය.
   ```
5. **Save** කරන්න. අපගේ JS engine එක මඟින් Layout එකෙහි ඇති මෙම widget එක ස්වයංක්‍රීයව හඳුනාගෙන, පිටුවේ ලස්සන Product Card එකක් ලෙස පෙන්වනු ඇත!

---

### පියවර 4: කාණ්ඩ (Categories) වෙනස් කිරීම
වෙබ් අඩවියේ ඉහළින් පෙන්වන Navigation Categories වෙනස් කිරීමට, `blogger_theme.xml` හි **`categories-scroll`** div එක තුළ ඇති `href='/search/label/CategoryName'` කොටස් වෙනස් කරන්න. 

ඔබ Post එකක් ලියන විට එයට ලබාදුන් Label එක, Category Link එකේ ඇති නමට (Case Sensitive - අකුරු කැපිටල්/සිම්පල් වීම) සමාන විය යුතුය.

---

### Local Testing (පරීක්ෂා කිරීම)
ඔබට මෙම වෙබ් අඩවියේ ක්‍රියාකාරීත්වය Blogger එකට දැමීමට පෙර ඔබේ පරිගණකයෙන්ම පරීක්ෂා කර බැලීමට, මෙම ෆෝල්ඩරයේ ඇති **`test_layout.html`** ගොනුව Double Click කර Google Chrome හෝ වෙනත් Browser එකකින් ඕපන් කර බලන්න! 

එහි:
- **Add to Cart** වැඩ කරන ආකාරය
- **WhatsApp Checkout Form** එක
- **PayPal integration** එක
- **Search bar** එක සහ **Category filtering** ක්‍රියාත්මක වන ආකාරය

ප්‍රායෝගිකව අත්හදා බැලිය හැක!
