#Data Types




## **🚀 انواع داده (Data Types) در جاوا اسکریپت**  

در **جاوا اسکریپت**، داده‌ها به دو دسته‌ی کلی تقسیم می‌شوند:  
1. **داده‌های اولیه (Primitive)**  
2. **داده‌های غیر اولیه (Non-Primitive) یا پیچیده**  

---

## **✅ ۱. داده‌های اولیه (Primitive Data Types)**
🔹 این داده‌ها **مستقیماً در حافظه ذخیره می‌شوند** و **تغییرناپذیر (Immutable)** هستند.  
🔹 شامل **۷ نوع** زیر هستند:

| نوع داده | توضیح | مثال |
|----------|-------|------|
| **`string`** | متن و رشته | `"Hello"` |
| **`number`** | اعداد صحیح و اعشاری | `10`, `3.14` |
| **`bigint`** | اعداد بسیار بزرگ | `12345678901234567890n` |
| **`boolean`** | مقدار درست یا غلط | `true`, `false` |
| **`undefined`** | متغیر تعریف شده ولی مقدار ندارد | `let x;` |
| **`null`** | مقدار خالی | `let x = null;` |
| **`symbol`** | مقدار یکتا و منحصر‌به‌فرد | `Symbol("id")` |

### **🔹 مثال برای داده‌های اولیه**
```js
let name = "Ali"; // string
let age = 25;     // number
let isStudent = true; // boolean
let largeNumber = 12345678901234567890n; // bigint
let noValue = null; // null
let notDefined; // undefined
let uniqueId = Symbol("id"); // symbol

console.log(typeof name);        // "string"
console.log(typeof age);         // "number"
console.log(typeof isStudent);   // "boolean"
console.log(typeof largeNumber); // "bigint"
console.log(typeof noValue);     // "object" (باگ جاوا اسکریپت!)
console.log(typeof notDefined);  // "undefined"
console.log(typeof uniqueId);    // "symbol"
```

---

## **✅ ۲. داده‌های غیر اولیه (Non-Primitive Data Types)**
🔹 این داده‌ها **آبجکت (Object)** هستند و **می‌توانند شامل چند مقدار مختلف باشند**.  
🔹 شامل موارد زیر هستند:

| نوع داده | توضیح | مثال |
|----------|-------|------|
| **`object`** | مجموعه‌ای از داده‌ها به‌صورت کلید-مقدار | `{ name: "Ali", age: 25 }` |
| **`array`** | لیستی از مقادیر | `[1, 2, 3, 4]` |
| **`function`** | مجموعه‌ای از دستورات اجرایی | `function sayHello() {}` |

### **🔹 مثال برای داده‌های غیر اولیه**
```js
let person = { name: "Ali", age: 25 }; // object
let numbers = [1, 2, 3, 4]; // array
let greet = function() { console.log("Hello!"); }; // function

console.log(typeof person);  // "object"
console.log(typeof numbers); // "object" (آرایه در جاوا اسکریپت نوع object دارد!)
console.log(typeof greet);   // "function"
```

---

## **✅ تفاوت بین `Primitive` و `Non-Primitive`**
| ویژگی | Primitive | Non-Primitive |
|--------|-----------|--------------|
| **تغییرپذیری** | **تغییرناپذیر (Immutable)** | **تغییرپذیر (Mutable)** |
| **نحوه ذخیره‌سازی** | مستقیماً در حافظه ذخیره می‌شود | **آدرس در حافظه ذخیره می‌شود** |
| **مقدار در مقایسه** | مقدار مستقیماً مقایسه می‌شود | آدرس (Reference) مقایسه می‌شود |
| **مثال** | `string`, `number`, `boolean` | `object`, `array`, `function` |

### **🔹 مثال تفاوت در مقایسه مقدار**
```js
let a = 10;
let b = 10;
console.log(a === b); // true (چون مقدار مستقیم مقایسه می‌شود)

let obj1 = { name: "Ali" };
let obj2 = { name: "Ali" };
console.log(obj1 === obj2); // false (چون آدرس در حافظه متفاوت است)
```

---

## **🚀 نتیجه‌گیری**
✅ **داده‌های اولیه (`Primitive`)** شامل `string`, `number`, `boolean`, `undefined`, `null`, `bigint`, `symbol` هستند.  
✅ **داده‌های غیر اولیه (`Non-Primitive`)** شامل `object`, `array`, `function` هستند.  
✅ داده‌های اولیه **با مقدارشان مقایسه می‌شوند**، ولی داده‌های غیر اولیه **با آدرس‌شان در حافظه مقایسه می‌شوند**.  

