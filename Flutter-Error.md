# Flutter-এ সাধারণ এরর এবং সমাধান 🚀

Flutter ডেভেলপমেন্টের সময় দেখা দেওয়া সাধারণ কিছু এরর এবং তাদের সমাধানের তালিকা নিচে দেওয়া হলো। এই গাইডটি নতুন এবং অভিজ্ঞ ডেভেলপারদের জন্য সহায়ক হবে।

---

## 📌 সূচিপত্র

1. [🖥️ UI সম্পর্কিত এরর](#ui_সম্পর্কিত_এরর)
2. [⚙️ State ম্যানেজমেন্ট এরর](#state_ম্যানেজমেন্ট_এরর)
3. [📦 ডিপেন্ডেন্সি এবং প্যাকেজ এরর](#ডিপেন্ডেন্সি_এবং_প্যাকেজ_এরর)
4. [📱 প্ল্যাটফর্ম স্পেসিফিক এরর](#প্ল্যাটফর্ম_স্পেসিফিক_এরর)
5. [❗ অন্যান্য সাধারণ এরর](#অন্যান্য_সাধারণ_এরর)
6. [🔥 অতিরিক্ত সাধারণ এরর](#অতিরিক্ত_সাধারণ_এরর)
7. [✅ অতিরিক্ত টিপস](#অতিরিক্ত_টিপস)

---

## 🖥️ UI সম্পর্কিত এরর

### 🚫 ১. "A RenderFlex overflowed…"
- *কারণ*: Row/Column-এর চাইল্ড উইজেট স্ক্রিনের বাইরে চলে যায়।
- *সমাধান*: Expanded বা Flexible ব্যবহার করুন।

### 🚫 ২. "RenderBox was not laid out"
- *কারণ*: উইজেটের সাইজ (height/width) ডিফাইন করা নেই।
- *সমাধান*: SizedBox, Expanded, বা নির্দিষ্ট width/height দিন।

### 🚫 ৩. "Vertical viewport was given unbounded height"
- *কারণ*: ListView/GridView-কে Column-এর ভিতরে রাখা হয়েছে।
- *সমাধান*: ListView-কে Expanded দিয়ে র‍্যাপ করুন।

### 🚫 ৪. "setState() called during build"
- *কারণ*: build() মেথডের ভিতরে setState() কল করা হয়েছে।
- *সমাধান*: WidgetsBinding.addPostFrameCallback ব্যবহার করুন।

### 🚫 ৫. "The ScrollController is attached to multiple scroll views"
- *কারণ*: একই ScrollController একাধিক ListView/GridView-এ ব্যবহার করা হয়েছে।
- *সমাধান*: প্রতিটি স্ক্রোল ভিউয়ের জন্য আলাদা ScrollController ব্যবহার করুন।

---

## ⚙️ State ম্যানেজমেন্ট এরর

### 🚫 ৬. "No MaterialLocalizations found"
- *কারণ*: MaterialApp বা CupertinoApp রুটে নেই।
- *সমাধান*: MaterialApp দিয়ে অ্যাপ র‍্যাপ করুন।

### 🚫 ৭. "Incorrect use of ParentDataWidget (e.g., Expanded/Flexible)"
- *কারণ*: Expanded সরাসরি Row/Column-এর বাইরে ব্যবহার করা হয়েছে।
- *সমাধান*: শুধুমাত্র Row/Column-এর চাইল্ড হিসেবে Expanded রাখুন।

---

## 📦 ডিপেন্ডেন্সি এবং প্যাকেজ এরর

### 🚫 ৮. "Null check operator used on a null value (!)"
- *কারণ*: null অবজেক্টে ! (non-null assertion) ব্যবহার করা হয়েছে।
- *সমাধান*: ?, ??, বা if (variable != null) ব্যবহার করুন।

### 🚫 ৯. "PlatformException: Unable to load asset"
- *কারণ*: pubspec.yaml-এ অ্যাসেট পাথ ভুল বা flutter pub get রান করা হয়নি।
- *সমাধান*: অ্যাসেট পাথ চেক করুন এবং flutter pub get রান করুন।

### 🚫 ১১. "Dependencies were not found"
- *কারণ*: প্যাকেজ ভার্সন কনফ্লিক্ট বা ইন্টারনেট সংযোগ সমস্যা।
- *সমাধান*: flutter pub upgrade বা pubspec.yaml চেক করুন।

---

## 📱 প্ল্যাটফর্ম স্পেসিফিক এরর

### 🚫 ১৪. "MissingPluginException"
- *কারণ*: প্ল্যাটফর্ম-স্পেসিফিক কোড (Android/iOS) লোড হয়নি।
- *সমাধান*: flutter clean ও প্ল্যাটফর্ম ফোল্ডার রিবিল্ড করুন।

---

## ❗ অন্যান্য সাধারণ এরর

### 🚫 ১০. "Scaffold.of() called with a context that does not contain a Scaffold"
- *কারণ*: Scaffold-এর বাইরে Scaffold.of(context) কল করা হয়েছে।
- *সমাধান*: Builder উইজেট ব্যবহার করুন অথবা GlobalKey<ScaffoldState> ব্যবহার করুন।

### 🚫 ১২. "Bad state: Future already completed"
- *কারণ*: Completer বা Future একাধিকবার কমপ্লিট করা হয়েছে।
- *সমাধান*: completer.isCompleted চেক করুন।

### 🚫 ১৩. "Key collisions in Widget tree"
- *কারণ*: একই Key একাধিক উইজেটে ব্যবহার করা হয়েছে।
- *সমাধান*: UniqueKey() বা ValueKey() ব্যবহার করুন।

### 🚫 ১৫. "MediaQuery.of() called with a context that does not contain a MediaQuery"
- *কারণ*: MaterialApp-এর বাইরে MediaQuery.of(context) কল করা হয়েছে।
- *সমাধান*: MediaQuery উইজেট দিয়ে র‍্যাপ করুন।

---

## 🔥 অতিরিক্ত সাধারণ এরর

### 🚫 ১৬. "LateInitializationError: Field has not been initialized"
- *কারণ*: late কিওয়ার্ড ব্যবহার করে ভেরিয়েবল ইনিশিয়ালাইজ না করেই ব্যবহার করা হয়েছে।
- *সমাধান*: ইনিশিয়ালাইজেশন নিশ্চিত করুন অথবা late? বাদ দিয়ে ? ব্যবহার করুন।

### 🚫 ১৭. "type '_InternalLinkedHashMap<String, dynamic>' is not a subtype of type 'List<dynamic>'"
- *কারণ*: JSON পার্সিংয়ের সময় টাইপ মিসম্যাচ হয়েছে।
- *সমাধান*: JSON স্ট্রাকচার এবং টাইপ কাস্টিং সঠিক করুন।

### 🚫 ১৮. "setState() or markNeedsBuild() called during build"
- *কারণ*: UI রেন্ডার করার সময় স্টেট পরিবর্তন করা হয়েছে।
- *সমাধান*: WidgetsBinding.instance.addPostFrameCallback() ব্যবহার করুন।

### 🚫 ১৯. "Failed assertion: line xx: 'navigator != null': is not true."
- *কারণ*: Navigator.of(context) এমন কনটেক্সটে কল করা হয়েছে যেখানে Navigator নেই।
- *সমাধান*: সঠিক কনটেক্সট থেকে Navigator কল করুন।

### 🚫 ২০. "Unhandled Exception: FormatException: Unexpected character"
- *কারণ*: ইনভ্যালিড JSON ডাটা পার্সিং হয়েছে।
- *সমাধান*: JSON ডাটার ভ্যালিডিটি চেক করুন।

### 🚫 ২১. "Cannot provide both a color and a decoration"
- *কারণ*: একই Container-এ color ও decoration একসাথে ব্যবহার করা হয়েছে যেখানে decoration-এ color আছে।
- *সমাধান*: color অথবা decoration থেকে একটি সরান।

### 🚫 ২২. "Unhandled Exception: NoSuchMethodError: The method 'xyz' was called on null"
- *কারণ*: null ভ্যালুতে মেথড কল হয়েছে।
- *সমাধান*: null চেক ব্যবহার করুন অথবা ? অপারেটর লাগান।

### 🚫 ২৩. "Unhandled Exception: MissingPluginException(No implementation found for method...)"
- *কারণ*: প্লাগইনের প্ল্যাটফর্ম কোড লোড হয়নি।
- *সমাধান*: flutter clean, flutter pub get ও অ্যাপ রিবিল্ড করুন।

---

## ✅ অতিরিক্ত টিপস

- *Hot Reload না কাজ করলে*: flutter clean + অ্যাপ রিস্টার্ট করুন।
- *ডিবাগিং*: debugPrint() বা flutter logs ব্যবহার করুন।
- *প্যাকেজ ক্যাশে সমস্যা হলে*: flutter pub cache repair রান করুন।

---

*এই গাইডটি ফলো করলে অনেক সাধারণ সমস্যার সমাধান সহজেই করা যাবে। Happy Fluttering!*
