# Resume

ChatGPT
بسم الله الرحمن الرحيم

النهاردة هنتكلم عن البرمجة الكائنية التوجه (OOP)، ودي تعني البرمجة اللي بتعتمد على الكائنات (Objects) بدلًا من استخدام بيانات مجردة فقط.

إزاي يعني؟
تخيل عندك مصنع، المصنع ده عبارة عن هيكل تنظيمي بيتكون من المدير، وبعده النائب، ثم المساعد، وبعد كده أقسام زي المالية والموارد البشرية، وكل قسم فيه موظفين بيقوموا بوظائف محددة. فيه عمليات بتحصل بين الأشخاص داخل كل قسم، وعمليات تانية بتحصل بين الأقسام وبعضها.

لما نيجي نحول الهيكل ده إلى كود، أسهل طريقة هي استخدام OOP.

ليه نستخدم OOP؟
لأنها بتوفر طريقة منظمة وسهلة لتمثيل الكيانات دي في صورة كود، بحيث نقدر:
✅ نعيد استخدام الكود بسهولة.
✅ ننظم البيانات بشكل يشبه الواقع.
✅ نحمي البيانات الحساسة.

إزاي بنطبق ده في الكود؟
هنبدأ بتقسيم هيكل الشركة إلى كائنات (Objects)، وكل كائن بيكون ليه خصائص (Properties) ووظائف (Methods).

1. الكائنات (Objects) وتمثيل الموظفين
لكل موظف بيانات أساسية زي:

الاسم
السن
العنوان
القسم اللي بيشتغل فيه
الرقم القومي
العمليات اللي بيقوم بيها
بدل ما نخزن البيانات دي في متغيرات منفصلة، هنستخدم الكائنات (Objects):

javascript
نسخ
تحرير
const employee = {
    name: "Ahmed",
    age: 30,
    department: "Finance",
    getInfo: function() {
        console.log(`${this.name} works in ${this.department} department.`);
    }
};

employee.getInfo(); // Ahmed works in Finance department.
2. الكلاسات (Classes) – القالب الأساسي للكائنات
لو عندنا موظفين كتير، بدل ما نكرر نفس الكود لكل موظف، هنستخدم الكلاسات (Classes) لإنشاء قالب لكل الموظفين.

javascript
نسخ
تحرير
class Employee {
    constructor(name, age, department) {
        this.name = name;
        this.age = age;
        this.department = department;
    }

    getInfo() {
        console.log(`${this.name} works in ${this.department} department.`);
    }
}

// إنشاء كائنات جديدة باستخدام الكلاس
const emp1 = new Employee("Ahmed", 30, "Finance");
const emp2 = new Employee("Mona", 25, "HR");

emp1.getInfo(); // Ahmed works in Finance department.
emp2.getInfo(); // Mona works in HR department.
3. الوراثة (Inheritance) – إنشاء أقسام متخصصة
بعض الموظفين قد يكونوا مديرين أو مطورين، وهنا نقدر نستخدم الوراثة (Inheritance) لإنشاء فئات متخصصة بناءً على الفئة الرئيسية.

javascript
نسخ
تحرير
class Manager extends Employee {
    constructor(name, age, department, teamSize) {
        super(name, age, department);
        this.teamSize = teamSize;
    }

    manage() {
        console.log(`${this.name} manages a team of ${this.teamSize} people.`);
    }
}

const manager = new Manager("Omar", 40, "IT", 10);
manager.getInfo(); // Omar works in IT department.
manager.manage(); // Omar manages a team of 10 people.
4. التغليف (Encapsulation) – حماية البيانات الحساسة
بعض البيانات، زي الراتب أو الرقم القومي، مش المفروض تكون متاحة لأي شخص. نقدر نحمي البيانات باستخدام التغليف (Encapsulation):

javascript
نسخ
تحرير
class Employee {
    #nationalID; // خاصية خاصة لا يمكن الوصول إليها من الخارج

    constructor(name, age, department, nationalID) {
        this.name = name;
        this.age = age;
        this.department = department;
        this.#nationalID = nationalID;
    }

    getNationalID() {
        return `Access Denied: You can't see the national ID.`;
    }
}

const emp = new Employee("Sara", 28, "HR", "123456789");
console.log(emp.name); // Sara
console.log(emp.getNationalID()); // Access Denied: You can't see the national ID.
console.log(emp.#nationalID); // ❌ خطأ - لا يمكن الوصول إليه مباشرة
الخلاصة
البرمجة الكائنية التوجه (OOP) بتساعدنا على تحويل البيانات إلى كائنات، مما يسهل تنظيم وإدارة البرامج الكبيرة. أهم المفاهيم فيها:
✅ Objects: لإنشاء البيانات على هيئة كائنات.
✅ Classes: لإنشاء قوالب للكائنات وتجنب تكرار الكود.
✅ Inheritance: لإعادة استخدام الكود وإنشاء أنواع متخصصة من الكائنات.
✅ Encapsulation: لحماية البيانات الحساسة ومنع الوصول غير المصرح به إليها.

باستخدام OOP، تقدر تبني برامج أكثر تنظيمًا، أمانًا، وسهولة في التطوير والصيانة! 🚀
