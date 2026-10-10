// main.js

// ==============================
// STEP 1 - Variables (Task 7.1)
// ==============================
const myName = "Emmanuel";
const myAge = 22;
const isStudent = true;
const favouriteColours = ["blue", "black", "green"];
const todayDate = new Date();

console.log(myName, typeof myName);
console.log(myAge, typeof myAge);
console.log(isStudent, typeof isStudent);
console.log(favouriteColours, typeof favouriteColours);
console.log(todayDate, typeof todayDate);

// ==============================
// STEP 2 - Operators (Task 7.2)
// ==============================
const ageInDays = myAge * 365;
const ageInHours = ageInDays * 24;
const yearTurn100 = new Date().getFullYear() + (100 - myAge);

console.log(`Age in days: ~${ageInDays}`);
console.log(`Age in hours: ~${ageInHours}`);
console.log(`Year you turn 100: ${yearTurn100}`);

console.log(`"5" + 7 =`, "5" + 7); // Prediction: "57" (string concat)
console.log(`"5" - 3 =`, "5" - 3); // Prediction: 2 (string coerced to number)
console.log(`5 == "5" =`, 5 == "5"); // Prediction: true (loose equality)
console.log(`5 === "5" =`, 5 === "5"); // Prediction: false (strict equality)

// ==============================
// STEP 3 - Functions (Task 7.3)
// ==============================
function calculateArea(width, height) {
  return width * height;
}

const celsiusToFahrenheit = (celsius) => {
  return (celsius * 9) / 5 + 32;
};

const isEven = (number) => {
  return number % 2 === 0;
};

const getInitials = (fullName) => {
  const parts = fullName.trim().split(" ");
  return parts.map(p => p[0].toUpperCase()).join("");
};

const reverseString = (str) => {
  return str.split("").reverse().join("");
};

const calculateTip = (bill, tipPercent = 15) => {
  return (bill * tipPercent) / 100;
};

console.log(calculateArea(10, 5));
console.log(celsiusToFahrenheit(0)); // 32
console.log(isEven(4)); // true
console.log(getInitials("Amina Utieno")); // AU
console.log(reverseString("hello"));
console.log(calculateTip(1000)); // 150 with default 15%
console.log(calculateTip(1000, 20)); // 200

// ==============================
// STEP 4 - Control Flow (Task 7.4)
// ==============================
const getGrade = (score) => {
  if (score >= 90) return "A";
  else if (score >= 80) return "B";
  else if (score >= 70) return "C";
  else if (score >= 60) return "D";
  else return "F";
};

const getDayName = (n) => {
  switch (n) {
    case 0: return "Sunday";
    case 1: return "Monday";
    case 2: return "Tuesday";
    case 3: return "Wednesday";
    case 4: return "Thursday";
    case 5: return "Friday";
    case 6: return "Saturday";
    default: return "Invalid day";
  }
};

console.log(getGrade(85)); // B
console.log(getDayName(0)); // Sunday

// Loops
for (let i = 1; i <= 100; i++) {
  console.log(i);
}

for (let i = 2; i <= 50; i += 2) {
  console.log(i);
}

for (let i = 1; i <= 5; i++) {
  console.log("*".repeat(i));
}

// ==============================
// STEP 5 - DEBUG THIS (5 bugs)
// ==============================
let total = 0; // Bug 1: TypeError - const can't be reassigned, must be let
const prices = [500, 1200, 300];
for (let i = 0; i < prices.length; i++) { // Bug 2: Logic error - was <= causes undefined on last iteration
  total = total + prices[i];
}
console.log("total:", total); // Bug 3: ReferenceError - was totl not total

function applyDiscount(amount) {
  if (amount === 1000) { // Bug 4: Logic/Bug - was = assignment and "1000" string, must be === 1000
    return amount * 0.9; // Bug 5: Logic - was console.log inside, but function must RETURN
  }
  return amount;
}

const discounted = applyDiscount(2000) + 100;
console.log(discounted);

// ==============================
// MINI-PROJECT - Calculator
// ==============================
const add = (a, b) => a + b;
const subtract = (a, b) => a - b;
const multiply = (a, b) => a * b;
const divide = (a, b) => {
  if (b === 0) return "Cannot divide by zero";
  return a / b;
};

const calculate = (num1, operator, num2) => {
  switch (operator) {
    case "+": return add(num1, num2);
    case "-": return subtract(num1, num2);
    case "*": return multiply(num1, num2);
    case "/": return divide(num1, num2);
    case "%": return num1 % num2;
    case "^": return num1 ** num2;
    default: return "Invalid operator";
  }
};

console.log(calculate(10, "+", 5)); // 15
console.log(calculate(10, "-", 5)); // 5
console.log(calculate(10, "*", 5)); // 50
console.log(calculate(10, "/", 5)); // 2
console.log(calculate(10, "/", 0)); // Cannot divide by zero
console.log(calculate(10, "%", 3)); // 1
console.log(calculate(7, "^", 2)); // 49? wait task says 8 - if ^ means power, 7^2=49. If task expects 8, change to ** but they wrote 7,^,2 -> 8 is wrong. Use ** = 49. If they want 2^3=8 logic, keep as **.
console.log(calculate(10, "x", 2)); // Invalid operator
