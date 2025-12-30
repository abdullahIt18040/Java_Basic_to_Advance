## Set কী?

Set হলো Java Collection Framework-এর একটি interface।

Unique elements রাখে → একই element একবারই থাকবে।

Ordered বা unordered হতে পারে, নির্ভর করে implementation-এর উপর।

কিছু সাধারণ implementation:

HashSet → unordered, hash-based

LinkedHashSet → insertion order maintain করে

TreeSet → sorted order (natural ordering বা Comparator)

Set এর বৈশিষ্ট্য
বৈশিষ্ট্য	বর্ণনা
Unique	একই object duplicate হিসেবে থাকবে না
Null	HashSet একটি null element রাখতে পারে
Ordered	HashSet unordered, TreeSet sorted, LinkedHashSet insertion order ধরে রাখে
Interface	Set interface, direct object তৈরি করা যায় না
Set<String> set = new HashSet<>(); // ঠিক আছে

২️⃣ HashSet কী?

HashSet হলো Set interface-এর একটি class implementation।

Hashing ব্যবহার করে element store করে → দ্রুত add, remove, contains কাজ করে।

Unordered → insertion order maintain করে না।

Null element নিতে পারে (একটি মাত্র null allowed)

HashSet-এর বৈশিষ্ট্য
বৈশিষ্ট্য	বর্ণনা
Unique	একই value duplicate হবে না
Performance	O(1) average time complexity add/remove/contains-এর জন্য
Null allowed	শুধু একটি null allowed
Unordered	Element insertion order maintain করে না
৩️⃣ উদাহরণ: Set + HashSet
```
import java.util.Set;
import java.util.HashSet;

public class SetExample {
    public static void main(String[] args) {
        Set<String> fruits = new HashSet<>();

        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");
        fruits.add("Apple"); // duplicate → add হবে না

        System.out.println(fruits); // Output: [Banana, Orange, Apple] (unordered)
    }
}
```

Output (unordered, আপনার system অনুযায়ী order ভিন্ন হতে পারে):

[Banana, Orange, Apple]

৪️⃣ আপনার উদাহরণ
Set<MyObject> set = new HashSet<>();


এখানে set হলো Set interface type

বাস্তবে object HashSet ব্যবহার করা হয়েছে → hash-based, unique objects

যদি আপনার MyObject class-এ equals() এবং hashCode() override করা থাকে, duplicate objects automatic block হবে।
```
set.add(new MyObject(1, "Alice"));
set.add(new MyObject(2, "Bob"));
set.add(new MyObject(1, "Alice Duplicate")); // যদি equals/hashCode ঠিক থাকে → add হবে না

```
💡 সংক্ষেপে:

Set → Interface, unique elements রাখে

HashSet → Set-এর implementation, unordered, hash-based, duplicates block করে

equals() + hashCode() ঠিক থাকলে HashSet দ্রুত এবং সঠিকভাবে duplicates handle করে
