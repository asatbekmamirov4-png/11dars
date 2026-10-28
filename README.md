# 11dars
const products = [
  { id: 1, name: "iPhone 15", price: 800, discount: 10, stock: 5 },
  { id: 2, name: "Samsung S24", price: 950, discount: 15, stock: 12 },
  { id: 3, name: "Redmi Note 13", price: 250, discount: 5, stock: 0 },
  { id: 4, name: "MacBook Air", price: 1200, discount: 20, stock: 3 },
  { id: 5, name: "iPad Pro", price: 1000, discount: 10, stock: 8 },
  { id: 6, name: "AirPods Pro", price: 250, discount: 0, stock: 20 },
];

const students = [
  { id: 1, name: "Ali", age: 18, score: 85 },
  { id: 2, name: "Vali", age: 17, score: 52 },
  { id: 3, name: "Madina", age: 19, score: 95 },
  { id: 4, name: "Sardor", age: 18, score: 67 },
  { id: 5, name: "Aziza", age: 17, score: 43 },
  { id: 6, name: "Jasur", age: 20, score: 76 },
];

// 1-masala
const expensiveProducts = products.filter(function (product) {
  return product.price > 800;
});
console.log(expensiveProducts);

// 2-masala
students.forEach(function (student) {
  console.log(student.name + " — " + student.score + " ball;");
});

// 3-masala
const discountedProducts = products.map(function (product) {
  const finalPrice = product.price - (product.price * product.discount / 10);
  return {
    name: product.name,
    price: product.price,
    discount: product.discount,
    finalPrice: finalPrice
  };
});
console.log(discountedProducts);

// 4-masala
const studentWithId4 = students.find(function (student) {
  return student.id === 4;
});
if (studentWithId4 !== undefined) {
  console.log(studentWithId4.name + " - " + studentWithId4.score);
} else {
  console.log("Talaba topilmadi");
}

// 5-masala
const isOutOfStock = products.some(function (product) {
  return product.stock === 0;
});
if (isOutOfStock === true) {
  console.log("Omborda tugagan mahsulot bor");
} else {
  console.log("Barcha mahsulotlar mavjud");
}

// 6-masala
const allPassed = students.every(function (student) {
  return student.score >= 60;
});
if (allPassed === true) {
  console.log("Barcha talabalar imtihondan o‘tdi");
} else {
  console.log("Imtihondan o‘tolmagan talabalar bor");
}

// 7-masala
const sortedProducts = products.slice().sort(function (a, b) {
  return a.price - b.price;
});
console.log(sortedProducts);

// 8-masala
const filteredStudents = students.filter(function (student) {
  return student.score >= 70;
});
const sortedStudents = filteredStudents.sort(function (a, b) {
  return b.score - a.score;
});
const topStudents = sortedStudents.map(function (student) {
  return { name: student.name, score: student.score };
});
console.log(topStudents);

// 9-masala
const filteredWithDiscount = products.filter(function (product) {
  return product.discount >= 10;
}).map(function (product) {
  const fPrice = product.price - (product.price * product.discount / 10);
  return {
    id: product.id,
    name: product.name,
    price: product.price,
    discount: product.discount,
    stock: product.stock,
    finalPrice: fPrice
  };
});
const hasExpensiveDiscounted = filteredWithDiscount.some(function (product) {
  return product.finalPrice > 800;
});
console.log("Mahsulotlar:", filteredWithDiscount);
console.log("800 dollardan qimmat mahsulot bormi?:", hasExpensiveDiscounted);

// 10-masala
const passedStudents = students.filter(function (student) {
  return student.score >= 60;
});
const sortedPassed = passedStudents.slice().sort(function (a, b) {
  return b.score - a.score;
});
const mappedStudents = sortedPassed.map(function (student) {
  return { name: student.name, score: student.score };
});
const topScorer = students.find(function (student) {
  return student.score > 90;
});
const hasTopScorer = students.some(function (student) {
  return student.score > 90;
});
const everyoneAbove40 = students.every(function (student) {
  return student.score >= 40;
});

students.forEach(function (student) {
  console.log("Ism: " + student.name + ", Ball: " + student.score);
});
console.log("90 dan yuqori ball olgan birinchi talaba:", topScorer);
console.log("Kamida bitta talaba 90 dan yuqori ball olganmi?:", hasTopScorer);
console.log("Barcha talabalar 40 dan yuqori ball olganmi?:", everyoneAbove40);
