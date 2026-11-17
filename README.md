বন্ধুদের মাসিক হিসাব — Android অ্যাপের প্রথম সংস্করণ
নির্ধারিত নিয়ম
সদস্য: ১০ জন
প্রত্যেকের মাসিক জমা: ৳১২,০০০
এক মাসে মোট নির্ধারিত জমা: ৳১,২০,০০০
একজন অ্যাডমিন হিসাব যোগ/পরিবর্তন করবেন
১০ জনই নিজেদের মোবাইল থেকে একই অনলাইন হিসাব দেখতে পারবেন
গুরুত্বপূর্ণ
এটি Flutter + Firebase-ভিত্তিক অ্যাপের সোর্স কোড। Firebase প্রকল্পের কনফিগারেশন না বসানো পর্যন্ত অ্যাপটি চালু হবে না। এই প্যাকেজটি APK নয়।
চালু করার ধাপ
কম্পিউটারে Flutter SDK এবং Android Studio ইনস্টল করুন।
টার্মিনালে এই ফোল্ডারে গিয়ে চালান: flutter create .
Firebase Console-এ নতুন Firebase project তৈরি করুন।
Firebase-এ Android app যোগ করুন। Android package name দিন: com.example.bondhuder_mashik_hishab
Authentication থেকে Email/Password sign-in চালু করুন।
Firestore Database তৈরি করুন।
FlutterFire CLI ইনস্টল করে চালান: dart pub global activate flutterfire_cli flutterfire configure এতে lib/firebase_options.dart তৈরি হবে।
firestore/firestore.rules-এর নিয়ম Firebase Console-এর Firestore Rules-এ প্রকাশ করুন।
Firebase Authentication-এ অ্যাডমিন এবং ১০ জন সদস্যের জন্য ১০টি email/password account তৈরি করুন।
Firestore-এ admins নামে collection তৈরি করুন। অ্যাডমিনের Authentication UID-কে document ID হিসেবে ব্যবহার করে একটি document তৈরি করুন। এতে অ্যাডমিন ছাড়া কেউ হিসাব পরিবর্তন করতে পারবে না।
Firestore-এ members collection-এ ১০টি document যোগ করুন। প্রতিটি document-এর field:
name: বন্ধুর নাম (String)
payments: Map (শুরুতে খালি {})
expenses collection-এ খরচের রেকর্ড যোগ করা যাবে:
note: খরচের কারণ (String)
amount: টাকা (Number)
date: তারিখ (String)
createdAt: Firestore server timestamp
চালান: flutter pub get flutter run
মাসিক জমা কীভাবে চিহ্নিত হবে
প্রতিটি সদস্যের payments map-এ মাসের key ব্যবহার করুন, যেমন 2026-11, এবং value true দিন। টাকা জমা না হলে false বা key অনুপস্থিত থাকবে। অ্যাপ বর্তমান মাসের অবস্থা দেখায়।
পরবর্তী কাজ
অ্যাপের ভেতর থেকেই অ্যাডমিনের জন্য জমা/খরচ যোগ করার ফর্ম
সদস্যদের নাম ও প্রোফাইল সম্পাদনা
মাস পরিবর্তন করে পুরোনো হিসাব দেখা
PDF/Excel রিপোর্ট ও ডেটা ব্যাকআপ
APK build এবং ফোনে ইনস্টল
প্রাথমিক সদস্য তালিকা
১. মো: সুমন ২. সাইফ ৩–১০. নাম পরে যোগ করতে হবে।
