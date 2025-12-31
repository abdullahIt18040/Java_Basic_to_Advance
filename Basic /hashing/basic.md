# Hashing
Hashing হলো এমন একটি পদ্ধতি যেখানে কোনো ডেটাকে একটি নির্দিষ্ট সংখ্যায় (hash code) রূপান্তর করা হয়, যাতে ডেটা দ্রুত সংরক্ষণ ও খুঁজে পাওয়া যায়।
জাভাতে Hashing বেশি ব্যবহৃত হয় HashMap, HashSet, Hashtable ইত্যাদি collection-এ।
```
Hash Code কী?

Hash Code হলো একটি integer মান, যা কোনো object থেকে hashCode() মেথড ব্যবহার করে তৈরি করা হয়।

int hash = object.hashCode();


এই hash code ব্যবহার করে জাভা ঠিক করে object টি কোন bucket-এ সংরক্ষণ হবে।

Hashing কেন দরকার?

খুব দ্রুত ডেটা খুঁজে পাওয়া যায়

Insert, Search, Delete দ্রুত হয়

বড় ডেটা হ্যান্ডেল করা সহজ হয়

Collection framework-এ ব্যাপক ব্যবহার

জাভাতে Hashing কোথায় ব্যবহৃত হয়?
1. HashMap

Key–Value আকারে ডেটা রাখে

Key এর উপর hashing হয়

Duplicate key রাখা যায় না

HashMap<Integer, String> map = new HashMap<>();
map.put(1, "Java");
map.put(2, "Spring");

System.out.println(map.get(1)); // Java

2. HashSet

শুধু unique value রাখে

ভিতরে HashMap ব্যবহার করে

Duplicate element গ্রহণ করে না

HashSet<String> set = new HashSet<>();
set.add("Java");
set.add("Java"); // গ্রহণ করবে না

System.out.println(set.size()); // 1

hashCode() এবং equals() এর সম্পর্ক

Hashing-এ এই দুইটি মেথড খুব গুরুত্বপূর্ণ।

নিয়মগুলো:

যদি দুইটি object equals() দিয়ে সমান হয়, তাহলে তাদের hashCode() অবশ্যই একই হবে

একই hash code হলেও object আলাদা হতে পারে

equals() দিয়ে আসল সমতা যাচাই করা হয়

Custom Class-এ Hashing উদাহরণ
class Student {
    int id;
    String name;

    Student(int id, String name) {
        this.id = id;
        this.name = name;
    }

    @Override
    public int hashCode() {
        return id;
    }

    @Override
    public boolean equals(Object obj) {
        Student s = (Student) obj;
        return this.id == s.id;
    }
}

Hash Collision কী?

যখন দুটি আলাদা object একই hash code তৈরি করে, তখন তাকে Hash Collision বলে।

জাভা collision হ্যান্ডেল করে:

Java 7 পর্যন্ত → Linked List
```

Java 8+ → Red-Black Tree (যখন bucket-এ element বেশি হয়)

1. Hashing কী?

উত্তর:
Hashing হলো এমন একটি টেকনিক যেখানে object বা key-কে একটি নির্দিষ্ট সংখ্যায় (hash code) রূপান্তর করা হয়, যাতে দ্রুত ডেটা সংরক্ষণ ও খোঁজা যায়।

2. hashCode() কেন দরকার?

উত্তর:
hashCode() ব্যবহার করে Java ঠিক করে object কোন bucket-এ যাবে। এতে search খুব দ্রুত হয় (O(1))।

3. equals() এবং hashCode() একসাথে কেন ব্যবহার হয়?

উত্তর:

hashCode() → bucket নির্ধারণ করে

equals() → একই bucket-এর ভিতরে object সত্যিই সমান কিনা যাচাই করে

4. equals() true কিন্তু hashCode() আলাদা হলে কী হবে?

উত্তর:
এটা Java-এর নিয়ম ভঙ্গ করবে এবং HashMap বা HashSet ঠিকভাবে কাজ করবে না (data duplicate বা miss হতে পারে)।

5. Hash Collision কী?

উত্তর:
যখন দুটি আলাদা object একই hash code তৈরি করে, তখন তাকে Hash Collision বলে।
