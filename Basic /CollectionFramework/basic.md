## Set কী?

Set হলো Java Collection Framework-এর একটি interface।

Unique elements রাখে → একই element একবারই থাকবে।

Ordered বা unordered হতে পারে, নির্ভর করে implementation-এর উপর।

কিছু সাধারণ implementation:
```
Map Implementations (সবচেয়ে গুরুত্বপূর্ণ অংশ)
🔹 1. HashMap
বৈশিষ্ট্য

Fastest (O(1))

Unordered

1টি null key allowed

Multiple null value allowed

Thread-safe না

Map<Integer, String> map = new HashMap<>();
map.put(1, "Java");
map.put(2, "Spring");
map.put(null, "NullKey");


📌 সবচেয়ে বেশি ব্যবহার হয়

🔹 2. LinkedHashMap
বৈশিষ্ট্য

Insertion order maintain করে

HashMap এর চেয়ে একটু slow

1টি null key allowed

Map<Integer, String> map = new LinkedHashMap<>();

🔹 3. TreeMap
বৈশিষ্ট্য

Sorted order (ascending)

null key allowed না

Red-Black Tree ব্যবহার করে

O(log n)

Map<Integer, String> map = new TreeMap<>();

🔹 4. Hashtable (Legacy)
বৈশিষ্ট্য

Thread-safe

null key/value allowed না

Slow

Map<Integer, String> map = new Hashtable<>();


❌ আজকাল ব্যবহার করা হয় না
✅ ConcurrentHashMap ব্যবহার করা হয়

🔹 5. ConcurrentHashMap
বৈশিষ্ট্য

Thread-safe

High performance

null key/value allowed না

Map<Integer, String> map = new ConcurrentHashMap<>();
```
