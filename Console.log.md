#Console.log

## **🚀 تفاوت `NaN`، `null` و `undefined` در جاوا اسکریپت**  

در جاوا اسکریپت، این سه مقدار **مفاهیم مختلفی** دارند و در شرایط متفاوتی استفاده می‌شوند. در اینجا تفاوت‌هایشان را بررسی می‌کنیم.  

---

## **✅ `NaN` (Not-a-Number - عدد نیست)**
🔹 مقدار `NaN` زمانی برمی‌گردد که یک عملیات ریاضی **نامعتبر** باشد، یعنی جاوا اسکریپت انتظار **عدد** داشته ولی چیزی دریافت کرده که عدد نیست.  

🔹 **ویژگی‌ها:**  
- نوع داده‌ی آن **`number`** است، اما خودش یک عدد **نامعتبر** محسوب می‌شود!  
- اگر محاسبه‌ای انجام شود که نتیجه‌ی منطقی عددی نداشته باشد، مقدار `NaN` برگردانده می‌شود.  
- `NaN` با هیچ مقداری (حتی خودش) برابر نیست!  

🔹 **مثال‌ها:**  
```js
console.log(0 / 0);        // NaN (تقسیم صفر بر صفر)
console.log("hello" * 3);  // NaN (جاوا اسکریپت نمی‌تواند رشته را در عدد ضرب کند)
console.log(Math.sqrt(-1));// NaN (جذر عدد منفی در ریاضی تعریف نشده است)

console.log(NaN === NaN);  // false (NaN با خودش برابر نیست!)
console.log(isNaN(NaN));   // true (بررسی می‌کند که مقدار NaN است)
```

🔹 **چطور `NaN` را چک کنیم؟**  
```js
console.log(isNaN("hello"));  // true (چون "hello" به عدد تبدیل نمی‌شود)
console.log(isNaN(123));      // false (چون 123 یک عدد معتبر است)
```

---

## **✅ `null` (خالی - مقدار ندارد)**
🔹 مقدار `null` یعنی یک **متغیر به‌طور عمدی مقدار ندارد**.  
🔹 **ویژگی‌ها:**  
- **یک مقدار خالی (empty)** است.  
- خودش مقدار `null` دارد ولی **نوع داده‌اش `object` است** (یک باگ قدیمی در جاوا اسکریپت!).  
- یعنی متغیر **وجود دارد اما مقدار ندارد**.  

🔹 **مثال‌ها:**  
```js
let x = null;
console.log(x);          // null
console.log(typeof x);   // object (یک باگ در جاوا اسکریپت!)

let person = { name: "Ali", age: null };
console.log(person.age); // null (یعنی مقدار ندارد)
```

🔹 **چطور `null` را چک کنیم؟**  
```js
console.log(x === null); // true
```

---

## **✅ `undefined` (تعریف نشده - مقدار اختصاص داده نشده)**
🔹 مقدار `undefined` یعنی یک متغیر **تعریف شده ولی هیچ مقداری ندارد**.  
🔹 **ویژگی‌ها:**  
- مقدار پیش‌فرض متغیرهایی که مقدار ندارند.  
- وقتی یک تابع بدون `return` اجرا شود، مقدار **`undefined`** برمی‌گردد.  
- وقتی به یک شیء (`object`) دسترسی داشته باشید که مقدار ندارد، مقدار **`undefined`** می‌گیرید.  

🔹 **مثال‌ها:**  
```js
let a;
console.log(a);        // undefined (چون مقدار نگرفته است)

function test() {}
console.log(test());   // undefined (چون چیزی return نکرده)

let obj = { name: "Ali" };
console.log(obj.age);  // undefined (چون age وجود ندارد)
```

🔹 **چطور `undefined` را چک کنیم؟**  
```js
console.log(typeof undefined); // "undefined"
console.log(a === undefined);  // true
```

---

## **📌 مقایسه کلی `NaN`، `null` و `undefined`**
| ویژگی        | `NaN` (عدد نامعتبر) | `null` (بدون مقدار) | `undefined` (تعریف نشده) |
|-------------|-------------------|----------------|----------------|
| **نوع داده**  | `number`          | `object`       | `undefined`    |
| **برابر با خودش؟** | ❌ `NaN !== NaN` | ✅ `null === null` | ✅ `undefined === undefined` |
| **مقایسه با `==`** | ❌ همیشه `false` | ✅ `null == undefined` (`true`) | ✅ `undefined == null` (`true`) |
| **مقایسه با `===`** | ❌ همیشه `false` | ❌ `null !== undefined` | ❌ `undefined !== null` |
| **چک کردن مقدار** | `isNaN(value)` | `value === null` | `typeof value === "undefined"` |

---

## **🚀 نتیجه‌گیری**
✅ **`NaN`** یعنی **نتیجه‌ی یک عملیات عددی نامعتبر است**.  
✅ **`null`** یعنی **متغیر مقدار ندارد اما عمداً خالی شده است**.  
✅ **`undefined`** یعنی **متغیر تعریف شده ولی مقدار نداشته است**.  






اینجا یک لیست از **تست‌های کوچک جاوا اسکریپت با `console.log`** آورده‌ام که می‌توانی در کنسول مرورگر اجرا کنی و خروجی را ببینی! 🚀  

---

### **✅ ۱. مقدار `undefined` در تابع بدون `return`**
```js
function test() {}
console.log(test()); // undefined
```

---

### **✅ ۲. جمع دو عدد**
```js
console.log(10 + 5); // 15
```

---

### **✅ ۳. نوع داده با `typeof`**
```js
console.log(typeof "Hello");  // string
console.log(typeof 123);      // number
console.log(typeof true);     // boolean
console.log(typeof {});       // object
console.log(typeof undefined); // undefined
console.log(typeof null);      // object (یک باگ قدیمی در JS!)
```

---

### **✅ ۴. چک کردن مقدار `NaN`**
```js
console.log(0 / 0);       // NaN
console.log(isNaN("123")); // false
console.log(isNaN("abc")); // true
```

---

### **✅ ۵. تفاوت `==` و `===`**
```js
console.log(5 == "5");  // true (مقایسه بدون بررسی نوع داده)
console.log(5 === "5"); // false (بررسی نوع داده هم انجام می‌شود)
```

---

### **✅ ۶. مقدار `null` و `undefined`**
```js
console.log(null == undefined);  // true
console.log(null === undefined); // false
```

---

### **✅ ۷. مقدار `true` و `false` در مقایسه با عدد**
```js
console.log(true + 1);   // 2 (چون `true` مقدار ۱ دارد)
console.log(false + 1);  // 1 (چون `false` مقدار ۰ دارد)
```

---

### **✅ ۸. تبدیل رشته به عدد (`parseInt` و `parseFloat`)**
```js
console.log(parseInt("42"));   // 42
console.log(parseInt("42px")); // 42 (اعداد اول را می‌گیرد)
console.log(parseFloat("3.14"));// 3.14
console.log(Number("42.5"));   // 42.5
console.log(+ "100");          // 100 (تبدیل سریع به عدد)
```

---

### **✅ ۹. چرخش آرایه (`reverse`)**
```js
console.log([1, 2, 3].reverse()); // [3, 2, 1]
```

---

### **✅ ۱۰. استفاده از `map` در آرایه**
```js
console.log([1, 2, 3].map(x => x * 2)); // [2, 4, 6]
```

---

### **✅ ۱۱. مقدار پیش‌فرض پارامتر در تابع**
```js
function greet(name = "مهمان") {
    console.log("سلام " + name + "!");
}
greet();       // خروجی: سلام مهمان!
greet("علی"); // خروجی: سلام علی!
```

---

### **✅ ۱۲. مقدار `Infinity` در جاوا اسکریپت**
```js
console.log(1 / 0); // Infinity
console.log(-1 / 0); // -Infinity
```

---

### **✅ ۱۳. پیدا کردن طول یک رشته**
```js
console.log("Hello".length); // 5
```

---

### **✅ ۱۴. ترکیب `join` روی آرایه**
```js
console.log(["علی", "مریم", "حسن"].join(" - ")); // "علی - مریم - حسن"
```

---

### **✅ ۱۵. بررسی مقدار `falsy` در شرط‌ها**
```js
console.log(Boolean(0));        // false
console.log(Boolean(""));       // false
console.log(Boolean(null));     // false
console.log(Boolean(undefined));// false
console.log(Boolean(NaN));      // false
console.log(Boolean(false));    // false
console.log(Boolean("Hello"));  // true
console.log(Boolean(100));      // true
```

