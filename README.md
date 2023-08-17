# 5 Minutes or Less: Refactoring

## Learn refactorings in just a few minutes - putting words to those neat, tidy things you hopefully do to your code

Refactoring is the process of changing and restructuring code without affecting its behavior. It's also a skill you'll need to have if you want to become senior as a developer/software engineer.

Nowadays we can literally ask a computer to write our code, which will undoubtedly lead to _more_ code in the future. Also, because more and more junior developers enter the field, and considering ~80% of budgets for IT projects are in maintenance, there just is no way around the fact that being good at cleaning and maintaining code is a critical skill for getting better in this field. The ability to detect and mitigate bad code is only going to grow over time.

In this repo I've compiled resources, examples, and tables from the seminal book on refactoring, called... you guessed it: [Refactoring: Improving the Design of Existing Code](https://www.goodreads.com/book/show/35135772-refactoring), written by Martin Fowler in 1999, now recently out in its second edition with code examples given in JavaScript. If you're a software engineer with any self-respect you owe it to yourself to get yourself a copythis book. Fowler is funny too, making the book pretty easy to digest. The reason it's a book, rather than a very long Markdown file like this, is because Fowler goes into detail about considerations and things to think about, for every single pattern. Buy it!

### Why this repo?

This is part of a series of bit-size educational resources I am putting together under the name "Five Minutes or Less", because you should be able to learn something new (every day?) in just a few minutes. I'm trying to make it as easy as possible to get such nuggets of new information in various software subjects.

Of course, in this case, you'd not learn _all_ refactorings in 5 minutes, but one or a few would be doable, as most aren't very complicated!

## Five Minutes or Less

- [SOLID](https://github.com/mikaelvesavuori/5-minutes-or-less-solid)
- [Design Patterns](https://github.com/mikaelvesavuori/5-minutes-or-less-design-patterns)
- [TypeScript/JavaScript patterns and features](https://github.com/mikaelvesavuori/5-minutes-or-less-typescript-js)

## Tooling recommendations

If you're a Visual Studio Code user, you should know there are already some [built-in functionality](https://code.visualstudio.com/docs/editor/refactoring) to assist with refactoring.

And while there are several plugins for refactoring, my favorite is [Abracadabra, refactor this!](https://marketplace.visualstudio.com/items?itemName=nicoespeon.abracadabra). Funky name, right? You can see some of its [full refactoring functionality at this page](https://github.com/nicoespeon/abracadabra/blob/main/REFACTORINGS.md).

## Other resources

There's also a fantastic site at [refactoring.guru](https://refactoring.guru/refactoring) that goes into far more detail than the list here. Highly recommended, and it has both lots of free content and paid material as well if you fancy going deep.

## Code smells and relevant refactorings

This list is reproduced from the book.

| Smell | Common Refactorings |
| ---  | --- |
| Alternative Classes with Different Interfaces | [Change Function Declaration](#change-function-declaration), [Move Function](#move-function), [Extract Superclass](#extract-superclass) |
| Comments                                      | [Extract Function](#extract-function), [Change Function Declaration](#change-function-declaration), [Introduce Assertion](#introduce-assertion) |
| Data Class                                    | [Encapsulate Record](#encapsulate-record), [Remove Setting Method](#remove-setting-method), [Move Function](#move-function), [Extract Function](#extract-function), [Split Phase](#split-phase) |
| Data Clumps                                   | [Extract Class](#extract-class), [Introduce Parameter Object](#introduce-parameter-object), [Preserve Whole Object](#preserve-whole-object) |
| Divergent Change                              | [Split Phase](#split-phase), [Move Function](#move-function), [Extract Function](#extract-function), [Extract Class](#extract-class) |
| Duplicated Code                               | [Extract Function](#extract-function), [Slide Statements](#slide-statements), [Pull Up Method](#pull-up-method) |
| Feature Envy                                  | [Move Function](#move-function), [Extract Function](#extract-function) |
| Global Data                                   | [Encapsulate Variable](#encapsulate-variable) |
| Insider Trading                               | [Move Function](#move-function), [Move Field](#move-field), [Hide Delegate](#hide-delegate), [Replace Subclass with Delegate](#replace-subclass-with-delegate), [Replace Superclass with Delegate](#replace-superclass-with-delegate) |
| Large Class                                   | [Extract Class](#extract-class), [Extract Superclass](#extract-superclass), [Replace Type Code with Subclasses](#replace-type-code-with-subclasses) |
| Lazy Element                                  | [Inline Function](#inline-function), [Inline Class](#inline-class), [Collapse Hierarchy](#collapse-hierarchy) |
| Long Function                                 | [Extract Function](#extract-function), [Replace Temp with Query](#replace-temp-with-query), [Introduce Parameter Object](#introduce-parameter-object), [Preserve Whole Object](#preserve-whole-object), [Replace Function with Command](#replace-function-with-command), [Decompose Conditional](#decompose-conditional), [Replace Conditional with Polymorphism](#replace-conditional-with-polymorphism), [Split Loop](#split-loop) |
| Long Parameter List                           | [Replace Parameter with Query](#replace-parameter-with-query), [Preserve Whole Object](#preserve-whole-object), [Introduce Parameter Object](#introduce-parameter-object), [Remove Flag Argument](#remove-flag-argument), [Combine Functions into Class](#combine-functions-into-class) |
| Loops                                         | [Replace Loop with Pipeline](#replace-loop-with-pipeline) |
| Message Chains                                | [Hide Delegate](#hide-delegate), [Extract Function](#extract-function), [Move Function](#move-function) |
| Middle Man                                    | [Remove Middle Man](#remove-middle-man), [Inline Function](#inline-function), [Replace Superclass with Delegate](#replace-superclass-with-delegate), [Replace Subclass with Delegate](#replace-subclass-with-delegate) |
| Mutable Data                                  | [Encapsulate Variable](#encapsulate-variable), [Split Variable](#split-variable), [Slide Statements](#slide-statements), [Extract Function](#extract-function), [Separate Query from Modifier](#separate-query-from-modifier), [Remove Setting Method](#remove-setting-method), [Replace Derived Variable with Query](#replace-derived-variable-with-query), [Combine Functions into Class](#combine-functions-into-class), [Combine Functions into Transform](#combine-functions-into-transform), [Change Reference to Value](#change-reference-to-value) |
| Mysterious Name                               | [Change Function Declaration](#change-function-declaration), [Rename Variable](#rename-variable), [Rename Field](#rename-field) |
| Primitive Obsession                           | [Replace Primitive with Object](#replace-primitive-with-object), [Replace Type Code with Subclasses](#replace-type-code-with-subclasses), [Replace Conditional with Polymorphism](#replace-conditional-with-polymorphism), [Extract Class](#extract-class), [Introduce Parameter Object](#introduce-parameter-object) |
| Refused Bequest                               | [Push Down Method](#push-down-method), [Push Down Field](#push-down-field), [Replace Subclass with Delegate](#replace-subclass-with-delegate), [Replace Superclass with Delegate](#replace-superclass-with-delegate) |
| Repeated Switches                             | [Replace Conditional with Polymorphism](#replace-conditional-with-polymorphism) |
| Shotgun Surgery                               | [Move Function](#move-function), [Move Field](#move-field), [Combine Functions into Class](#combine-functions-into-class), [Combine Functions into Transform](#combine-functions-into-transform), [Split Phase](#split-phase), [Inline Function](#inline-function), [Inline Class](#inline-class) |
| Speculative Generality                        | [Collapse Hierarchy](#collapse-hierarchy), [Inline Function](#inline-function), [Inline Class](#inline-class), [Change Function Declaration](#change-function-declaration), [Remove Dead Code](#remove-dead-code) |
| Temporary Field                               | [Extract Class](#extract-class), [Move Function](#move-function), [Introduce Special Case](#introduce-special-case) |

## Refactorings

All these refactorings are generated by ChatGPT 3.5 in August 2023, using the prompt:

```text
Give me fun, original, minimalist TypeScript examples for the following refactorings from Martin Fowler's book (2nd edition from 2018): [LIST]
```

To the best of my ability and knowledge they are validated as correct examples. I'll happily update if you find anything strange!

Also see [Martin Fowler's Refactoring catalog](https://refactoring.com/catalog/) for more.

### Running the code

You can either clone this repo or simply copy the individual examples into the [TypeScript playground](https://www.typescriptlang.org/play).

---

- [Change Function Declaration](#change-function-declaration) (Rename Function; Rename Method; Add Parameter; Remove Parameter; Change Signature)
- [Change Reference to Value](#change-reference-to-value)
- [Change Value to Reference](#change-value-to-reference)
- [Collapse Hierarchy](#collapse-hierarchy)
- [Combine Functions into Class](#combine-functions-into-class)
- [Combine Functions into Transform](#combine-functions-into-transform)
- [Consolidate Conditional Expression](#consolidate-conditional-expression)
- [Decompose Conditional](#decompose-conditional)
- [Encapsulate Collection](#encapsulate-collection)
- [Encapsulate Record](#encapsulate-record) (Replace Record with Data Class)
- [Encapsulate Variable](#encapsulate-variable) (Encapsulate Field; Self-Encapsulate Field)
- [Extract Class](#extract-class)
- [Extract Function](#extract-function)
- [Extract Superclass](#extract-superclass)
- [Extract Variable](#extract-variable) (Introduce Explaining Variable)
- [Hide Delegate](#hide-delegate)
- [Inline Class](#inline-class)
- [Inline Function](#inline-function) (Inline Method)
- [Inline Variable](#inline-variable) (Inline Temp)
- [Introduce Assertion](#introduce-assertion)
- [Introduce Parameter Object](#introduce-parameter-object)
- [Introduce Special Case](#introduce-special-case) (Introduce Null Object)
- [Move Field](#move-field)
- [Move Function](#move-function) (Move Method)
- [Move Statements into Function](#move-statements-into-function)
- [Move Statements to Callers](#move-statements-to-callers)
- [Parameterize Function](#parameterize-function) (Parameterize Method)
- [Preserve Whole Object](#preserve-whole-object)
- [Pull Up Constructor Body](#pull-up-constructor-body)
- [Pull Up Field](#pull-up-field)
- [Pull Up Method](#pull-up-method)
- [Push Down Field](#push-down-field)
- [Push Down Method](#push-down-method)
- [Remove Dead Code](#remove-dead-code)
- [Remove Flag Argument](#remove-flag-argument) (Replace Parameter with Explicit Methods)
- [Remove Middle Man](#remove-middle-man)
- [Remove Setting Method](#remove-setting-method)
- [Remove Subclass](#remove-subclass) (Replace Subclass with Fields)
- [Rename Field](#rename-field)
- [Rename Variable](#rename-variable)
- [Replace Command with Function](#replace-command-with-function)
- [Replace Conditional with Polymorphism](#replace-conditional-with-polymorphism)
- [Replace Constructor with Factory Function](#replace-constructor-with-factory-function) (Replace Constructor with Factory Method)
- [Replace Derived Variable with Query](#replace-derived-variable-with-query)
- [Replace Function with Command](#replace-function-with-command) (Replace Method with Method Object)
- [Replace Inline Code with Function Call](#replace-inline-code-with-function-call)
- [Replace Loop with Pipeline](#replace-loop-with-pipeline)
- [Replace Nested Conditional with Guard Clauses](#replace-nested-conditional-with-guard-clauses)
- [Replace Parameter with Query](#replace-parameter-with-query) (Replace Parameter with Method)
- [Replace Primitive with Object](#replace-primitive-with-object) (Replace Data Value with Object; Replace Type Code with Class)
- [Replace Query with Parameter](#replace-query-with-parameter)
- [Replace Subclass with Delegate](#replace-subclass-with-delegate)
- [Replace Superclass with Delegate](#replace-superclass-with-delegate) (Replace Inheritance with Delegation)
- [Replace Temp with Query](#replace-temp-with-query)
- [Replace Type Code with Subclasses](#replace-type-code-with-subclasses) (Extract Subclass; Replace Type Code with State/Strategy)
- [Separate Query from Modifier](#separate-query-from-modifier)
- [Slide Statements](#slide-statements) (Consolidate Duplicate Conditional Fragments)
- [Split Loop](#split-loop)
- [Split Phase](#split-phase)
- [Split Variable](#split-variable) (Remove Assignments to Parameters; Split Temp)
- [Substitute Algorithm](#substitute-algorithm)

Not in the 2nd edition:

- [Replace Control Flag with Break](#replace-control-flag-with-break) (Remove Control Flag)
- [Replace Error Code with Exception](#replace-error-code-with-exception)
- [Replace Exception with Precheck](#replace-exception-with-precheck) (Replace Exception with Test)
- [Replace Magic Literal](#replace-magic-literal) (Replace Magic Number with Symbolic Constant)
- [Return Modified Value](#return-modified-value)

---

### Change Function Declaration

**Aliases**: _Rename Function; Rename Method; Add Parameter; Remove Parameter; Change Signature_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/changeFunctionDeclaration.html).

```ts
// Before
function calculateCircleArea(radius: number): number {
  return Math.PI * radius * radius;
}

// After
class Circle {
  constructor(public radius: number) { }

  calculateArea(): number {
    return Math.PI * this.radius * this.radius;
  }
}
```

### Change Reference to Value

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/changeReferenceToValue.html).

```ts
// Before
class Temperature {
  constructor(public value: number) { }

  getFahrenheit(): number {
    return this.value * 9 / 5 + 32;
  }
}

// After
class CelsiusTemperature {
  constructor(public celsius: number) { }

  getFahrenheit(): number {
    return this.celsius * 9 / 5 + 32;
  }
}
```

### Change Value to Reference

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/changeValueToReference.html).

```ts
// Before
class Product {
  constructor(public name: string) { }
}

class Order {
  constructor(public product: Product) { }
}

// After
class ProductRegistry {
  private products: Map<string, Product> = new Map();

  getProduct(name: string): Product | undefined {
    return this.products.get(name);
  }

  addProduct(product: Product): void {
    this.products.set(product.name, product);
  }
}

class Order {
  constructor(public productName: string) { }
}
```

### Collapse Hierarchy

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/collapseHierarchy.html).

```ts
// Before
class Shape {
  constructor(public name: string) { }
}

class Circle extends Shape {
  constructor(public radius: number) {
    super('Circle');
  }

  calculateArea(): number {
    return Math.PI * this.radius * this.radius;
  }
}

// After
class Circle {
  constructor(public radius: number) { }

  calculateArea(): number {
    return Math.PI * this.radius * this.radius;
  }
}
```

### Combine Functions into Class

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/combineFunctionsIntoClass.html).

```ts
// Before
function formatName(firstName: string, lastName: string): string {
  return `${lastName}, ${firstName}`;
}

// After
class NameFormatter {
  constructor(public firstName: string, public lastName: string) { }

  format(): string {
    return `${this.lastName}, ${this.firstName}`;
  }
}
```

### Combine Functions into Transform

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/combineFunctionsIntoTransform.html).

```ts
// Before
function capitalizeWord(word: string): string {
  return word.charAt(0).toUpperCase() + word.slice(1);
}

function formatTitle(title: string): string {
  const words = title.split(' ');
  const capitalizedWords = words.map(capitalizeWord);
  return capitalizedWords.join(' ');
}

// After
class TitleFormatter {
  constructor(public title: string) { }

  format(): string {
    const words = this.title.split(' ');
    const capitalizedWords = words.map(this.capitalizeWord);
    return capitalizedWords.join(' ');
  }

  private capitalizeWord(word: string): string {
    return word.charAt(0).toUpperCase() + word.slice(1);
  }
}
```

### Consolidate Conditional Expression

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/consolidateConditionalExpression.html).

```ts
// Before
function calculateBonus(salary: number, yearsWorked: number, isTopPerformer: boolean): number {
  let bonus = 0;

  if (isTopPerformer) {
    bonus += salary * 0.2;
  }

  if (yearsWorked >= 5) {
    bonus += salary * 0.1;
  }

  return bonus;
}

// After
function calculateBonus(salary: number, yearsWorked: number, isTopPerformer: boolean): number {
  let bonus = 0;

  if (isTopPerformer || yearsWorked >= 5) {
    bonus += salary * 0.2;
  }

  return bonus;
}
```

### Decompose Conditional

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/decomposeConditional.html).

```ts
// Before
function calculateShippingCost(orderTotal: number, isPriority: boolean): number {
  let shippingCost = 0;

  if (orderTotal > 100) {
    shippingCost = isPriority ? 10 : 20;
  } else {
    shippingCost = isPriority ? 15 : 30;
  }

  return shippingCost;
}

// After
class ShippingCalculator {
  calculateShippingCost(orderTotal: number, isPriority: boolean): number {
    if (orderTotal > 100) {
      return isPriority ? 10 : 20;
    } else {
      return isPriority ? 15 : 30;
    }
  }
}
```

### Encapsulate Collection

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/encapsulateCollection.html).

```ts
// Before
class ShoppingCart {
  items: string[] = [];

  addItem(item: string): void {
    this.items.push(item);
  }

  removeItem(item: string): void {
    const index = this.items.indexOf(item);
    if (index !== -1) {
      this.items.splice(index, 1);
    }
  }

  getItems(): string[] {
    return this.items;
  }
}

// After
class ShoppingCart {
  private items: string[] = [];

  addItem(item: string): void {
    this.items.push(item);
  }

  removeItem(item: string): void {
    const index = this.items.indexOf(item);
    if (index !== -1) {
      this.items.splice(index, 1);
    }
  }

  getItemCount(): number {
    return this.items.length;
  }
}
```

### Encapsulate Record

**Aliases**: _Replace Record with Data Class_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/encapsulateRecord.html).

```ts
// Before
const employee = {
  firstName: "John",
  lastName: "Doe",
  age: 30,
  salary: 50000,
};

// After
class Employee {
  constructor(
    public firstName: string,
    public lastName: string,
    public age: number,
    public salary: number
  ) { }
}

const employee = new Employee("John", "Doe", 30, 50000);
```

### Encapsulate Variable

**Aliases**: _Encapsulate Field; Self-Encapsulate Field_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/encapsulateVariable.html).

```ts
// Before
let discount = 0.15;

function applyDiscount(price: number): number {
  return price * (1 - discount);
}

// After
class DiscountManager {
  private static discount = 0.15;

  static applyDiscount(price: number): number {
    return price * (1 - this.discount);
  }
}
```

### Extract Class

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/extractClass.html).

```ts
// Before
class Order {
  customerName: string;
  customerAddress: string;
  items: string[];

  constructor(customerName: string, customerAddress: string, items: string[]) {
    this.customerName = customerName;
    this.customerAddress = customerAddress;
    this.items = items;
  }

  printOrderDetails(): void {
    console.log(`Customer: ${this.customerName}`);
    console.log(`Address: ${this.customerAddress}`);
    console.log(`Items: ${this.items.join(', ')}`);
  }
}

// After
class Customer {
  constructor(public name: string, public address: string) { }
}

class Order {
  constructor(public customer: Customer, public items: string[]) { }

  printOrderDetails(): void {
    console.log(`Customer: ${this.customer.name}`);
    console.log(`Address: ${this.customer.address}`);
    console.log(`Items: ${this.items.join(', ')}`);
  }
}
```

### Extract Function

**Aliases**: _Extract Method_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/extractFunction.html).

```ts
// Before
function calculateTotalPrice(cart: number[], taxRate: number): number {
  let total = 0;
  for (const item of cart) {
    total += item;
  }
  return total * (1 + taxRate);
}

// After
function calculateSubtotal(cart: number[]): number {
  let subtotal = 0;
  for (const item of cart) {
    subtotal += item;
  }
  return subtotal;
}

function calculateTotalPrice(subtotal: number, taxRate: number): number {
  return subtotal * (1 + taxRate);
}
```

### Extract Superclass

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/extractSuperclass.html).

```ts
// Before
class Employee {
  name: string;
  id: number;

  constructor(name: string, id: number) {
    this.name = name;
    this.id = id;
  }

  // Employee-specific methods...
}

class Manager extends Employee {
  teamSize: number;

  constructor(name: string, id: number, teamSize: number) {
    super(name, id);
    this.teamSize = teamSize;
  }

  // Manager-specific methods...
}

class Developer extends Employee {
  programmingLanguage: string;

  constructor(name: string, id: number, programmingLanguage: string) {
    super(name, id);
    this.programmingLanguage = programmingLanguage;
  }

  // Developer-specific methods...
}

// After
class Employee {
  name: string;
  id: number;

  constructor(name: string, id: number) {
    this.name = name;
    this.id = id;
  }

  // Employee-specific methods...
}

class Manager extends Employee {
  teamSize: number;

  constructor(name: string, id: number, teamSize: number) {
    super(name, id);
    this.teamSize = teamSize;
  }

  // Manager-specific methods...
}

class Developer extends Employee {
  programmingLanguage: string;

  constructor(name: string, id: number, programmingLanguage: string) {
    super(name, id);
    this.programmingLanguage = programmingLanguage;
  }

  // Developer-specific methods...
}

class Salesperson extends Employee {
  region: string;

  constructor(name: string, id: number, region: string) {
    super(name, id);
    this.region = region;
  }

  // Salesperson-specific methods...
}
```

### Extract Variable

**Aliases**: _Introduce Explaining Variable_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/extractVariable.html).

```ts
// Before
// Before
function calculateTotalPrice(quantity: number, pricePerUnit: number, taxRate: number): number {
  const totalPrice = quantity * pricePerUnit;
  return totalPrice + totalPrice * taxRate;
}

// After
function calculateTotalPrice(quantity: number, pricePerUnit: number, taxRate: number): number {
  const basePrice = quantity * pricePerUnit;
  const taxAmount = basePrice * taxRate;
  return basePrice + taxAmount;
}
```

### Hide Delegate

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/hideDelegate.html).

```ts
// Before
class Department {
  manager: Employee;

  constructor(manager: Employee) {
    this.manager = manager;
  }

  getManager(): Employee {
    return this.manager;
  }
}

class Employee {
  name: string;

  constructor(name: string) {
    this.name = name;
  }
}

// After
class Department {
  manager: Employee;

  constructor(manager: Employee) {
    this.manager = manager;
  }

  getManagerName(): string {
    return this.manager.name;
  }
}
```

### Inline Class

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/inlineClass.html).

```ts
// Before
class Address {
  street: string;
  city: string;
  country: string;

  constructor(street: string, city: string, country: string) {
    this.street = street;
    this.city = city;
    this.country = country;
  }
}

class Customer {
  name: string;
  address: Address;

  constructor(name: string, address: Address) {
    this.name = name;
    this.address = address;
  }
}

// After
class Customer {
  name: string;
  street: string;
  city: string;
  country: string;

  constructor(name: string, street: string, city: string, country: string) {
    this.name = name;
    this.street = street;
    this.city = city;
    this.country = country;
  }
}
```

### Inline Function

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/inlineFunction.html).

```ts
// Before
function calculateTotal(price: number, quantity: number): number {
  return applyDiscount(price * quantity);
}

function applyDiscount(amount: number): number {
  return amount * 0.9;
}

// After
function calculateTotal(price: number, quantity: number): number {
  return price * quantity * 0.9;
}
```

### Inline Variable

**Aliases**: _Inline Temp_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/inlineVariable.html).

```ts
// Before
function calculateTotalPrice(quantity: number, pricePerUnit: number, taxRate: number): number {
  const basePrice = quantity * pricePerUnit;
  const taxAmount = basePrice * taxRate;
  return basePrice + taxAmount;
}

// After
function calculateTotalPrice(quantity: number, pricePerUnit: number, taxRate: number): number {
  return quantity * pricePerUnit + quantity * pricePerUnit * taxRate;
}
```

### Introduce Assertion

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/introduceAssertion.html).

```ts
// Before
function calculateDiscountedPrice(price: number, discount: number): number {
  if (discount < 0 || discount > 1) {
    throw new Error("Invalid discount percentage");
  }
  return price * (1 - discount);
}

// After
function calculateDiscountedPrice(price: number, discount: number): number {
  console.assert(discount >= 0 && discount <= 1, "Invalid discount percentage");
  return price * (1 - discount);
}
```

### Introduce Parameter Object

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/introduceParameterObject.html).

```ts
// Before
function createOrder(customer: string, product: string, quantity: number): Order {
  // ...
}

// After
class OrderInfo {
  constructor(public customer: string, public product: string, public quantity: number) { }
}

function createOrder(orderInfo: OrderInfo): Order {
  // ...
}
```

### Introduce Special Case

**Aliases**: _Introduce Null Object_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/introduceSpecialCase.html).

```ts
// Before
function calculateDiscountedPrice(price: number, discount: number): number {
  if (discount === 0) {
    return price;
  }
  return price * (1 - discount);
}

// After
class Discount {
  constructor(public value: number) { }

  apply(price: number): number {
    if (this.value === 0) {
      return price;
    }
    return price * (1 - this.value);
  }
}
```

### Move Field

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/moveField.html).

```ts
// Before
class Customer {
  name: string;
}

class Order {
  customer: Customer;

  constructor(customer: Customer) {
    this.customer = customer;
  }
}

// After
class Order {
  constructor(public customer: Customer) { }
}
```

### Move Function

**Aliases**: _Move Method_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/moveFunction.html).

```ts
// Before
class Account {
  // ...
}

class AccountType {
  isPremium(): boolean {
    return true;
  }
}

// After
class Account {
  constructor(private type: AccountType) { }

  isPremium(): boolean {
    return this.type.isPremium();
  }
}
```

### Move Statements into Function

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/moveStatementsIntoFunction.html).

```ts
// Before
function printInvoice(order: Order): void {
  console.log("Invoice:");
  console.log(`Customer: ${order.customer}`);
  console.log(`Total: ${order.total}`);
}

// After
class Order {
  printInvoice(): void {
    console.log("Invoice:");
    console.log(`Customer: ${this.customer}`);
    console.log(`Total: ${this.total}`);
  }
}
```

### Move Statements to Callers

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/moveStatementsToCallers.html).

```ts
// Before
function applyDiscount(order: Order): void {
  if (order.total > 100) {
    order.total *= 0.9;
  }
}

// After
class Order {
  applyDiscount(): void {
    if (this.total > 100) {
      this.total *= 0.9;
    }
  }
}
```

### Parameterize Function

**Aliases**: _Parameterize Method_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/parameterizeFunction.html).

```ts
// Before
function calculateTotal(price: number, quantity: number, taxRate: number): number {
  return price * quantity * (1 + taxRate);
}

// After
function calculateTotal(price: number, quantity: number, taxRate: number): number {
  return price * quantity * (1 + taxRate);
}
```

### Preserve Whole Object

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/preserveWholeObject.html).

```ts
// Before
function orderDelivery(customer: Customer): void {
  const address = customer.address;
  // ... process the address for delivery
}

// After
function orderDelivery(address: Address): void {
  // ... process the address for delivery
}
```

### Pull Up Constructor Body

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/pullUpConstructorBody.html).

```ts
// Before
class Product {
  constructor(public name: string) {
    console.log("Product created.");
  }
}

class Book extends Product {
  constructor(name: string, public author: string) {
    super(name);
  }
}

// After
class Product {
  constructor(public name: string) { }
}

class Book extends Product {
  constructor(name: string, public author: string) {
    super(name);
    console.log("Product created.");
  }
}
```

### Pull Up Field

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/pullUpField.html).

```ts
// Before
class Vehicle {
  // ...
}

class Car extends Vehicle {
  engineType: string;
  // ...
}

class Bicycle extends Vehicle {
  // ...
}

// After
class Vehicle {
  engineType: string;
  // ...
}

class Car extends Vehicle {
  // ...
}

class Bicycle extends Vehicle {
  // ...
}
```

### Pull Up Method

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/pullUpMethod.html).

```ts
// Before
class Employee {
  // ...
}

class Salesperson extends Employee {
  calculateCommission(salesAmount: number): number {
    return salesAmount * 0.1;
  }
}

class Manager extends Employee {
  // ...
}

// After
class Employee {
  calculateCommission(salesAmount: number): number {
    return salesAmount * 0.1;
  }
}

class Salesperson extends Employee {
  // ...
}

class Manager extends Employee {
  // ...
}
```

### Push Down Field

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/pushDownField.html).

```ts
// Before
class Vehicle {
  // ...
}

class Car extends Vehicle {
  color: string;
  // ...
}

class Bicycle extends Vehicle {
  // ...
}

// After
class Vehicle {
  // ...
}

class Car extends Vehicle {
  color: string;
  // ...
}

class Bicycle extends Vehicle {
  // ...
}
```

### Push Down Method

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/pushDownMethod.html).

```ts
// Before
class Employee {
  // ...
}

class Salesperson extends Employee {
  calculateCommission(salesAmount: number): number {
    return salesAmount * 0.1;
  }
}

class Manager extends Employee {
  // ...
}

// After
class Employee {
  // ...
}

class Salesperson extends Employee {
  // ...
}

class Manager extends Employee {
  calculateCommission(salesAmount: number): number {
    return salesAmount * 0.05;
  }
}
```

### Remove Dead Code

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/removeDeadCode.html).

```ts
// Before
function calculateTotal(price: number, quantity: number): number {
  // Dead code, never used
  const taxRate = 0.1;
  return price * quantity * (1 + taxRate);
}

// After
function calculateTotal(price: number, quantity: number): number {
  return price * quantity;
}
```

### Remove Flag Argument

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/removeFlagArgument.html).

```ts
// Before
function sendNotification(message: string, isUrgent: boolean): void {
  if (isUrgent) {
    // Send urgent notification
  } else {
    // Send normal notification
  }
}

// After
function sendUrgentNotification(message: string): void {
  // Send urgent notification
}

function sendNormalNotification(message: string): void {
  // Send normal notification
}
```

### Remove Middle Man

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/removeMiddleMan.html).

```ts
// Before
class Department {
  manager: Employee;

  constructor(manager: Employee) {
    this.manager = manager;
  }

  getManager(): Employee {
    return this.manager;
  }
}

// After
class Department {
  constructor(public manager: Employee) { }
}
```

### Remove Setting Method

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/removeSettingMethod.html).

```ts
// Before
class Person {
  name: string;

  setName(name: string): void {
    this.name = name;
  }
}

// After
class Person {
  constructor(public name: string) { }
}
```

### Remove Subclass

**Aliases**: _Replace Subclass with Fields_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/removeSubclass.html).

```ts
// Before
class Employee {
  // ...
}

class Salesperson extends Employee {
  // ...
}

class Manager extends Employee {
  // ...
}

// After
class Employee {
  // ...
}
```

### Rename Field

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/renameField.html).

```ts
// Before
class Person {
  fn: string;
  ln: string;

  constructor(firstName: string, lastName: string) {
    this.fn = firstName;
    this.ln = lastName;
  }
}

// After
class Person {
  constructor(public firstName: string, public lastName: string) { }
}
```

### Rename Variable

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/renameVariable.html).

```ts
// Before
function calculateTotal(prc: number, qty: number): number {
  return prc * qty;
}

// After
function calculateTotal(price: number, quantity: number): number {
  return price * quantity;
}
```

### Replace Command with Function

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceCommandWithFunction.html).

```ts
// Before
class BankAccount {
  balance: number;

  constructor(initialBalance: number) {
    this.balance = initialBalance;
  }

  withdraw(amount: number): void {
    this.balance -= amount;
  }
}

// After
class BankAccount {
  balance: number;

  constructor(initialBalance: number) {
    this.balance = initialBalance;
  }

  deduct(amount: number): void {
    this.balance -= amount;
  }
}
```

### Replace Conditional with Polymorphism

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceConditionalWithPolymorphism.html).

```ts
// Before
class Employee {
  type: string;
  monthlySalary: number;
  commission: number;

  constructor(type: string, monthlySalary: number, commission: number) {
    this.type = type;
    this.monthlySalary = monthlySalary;
    this.commission = commission;
  }

  calculatePay(): number {
    if (this.type === "fullTime") {
      return this.monthlySalary;
    } else if (this.type === "commissioned") {
      return this.monthlySalary + this.commission;
    }
  }
}

// After
class Employee {
  calculatePay(): number {
    throw new Error("Abstract method");
  }
}

class FullTimeEmployee extends Employee {
  constructor(private monthlySalary: number) {
    super();
  }

  calculatePay(): number {
    return this.monthlySalary;
  }
}

class CommissionedEmployee extends Employee {
  constructor(private monthlySalary: number, private commission: number) {
    super();
  }

  calculatePay(): number {
    return this.monthlySalary + this.commission;
  }
}
```

### Replace Constructor with Factory Function

**Aliases**: _Replace Constructor with Factory Method_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceConstructorWithFactoryFunction.html).

```ts
// Before
class Person {
  name: string;
  age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
}

// After
class Person {
  private constructor(public name: string, public age: number) { }

  static createPerson(name: string, age: number): Person {
    return new Person(name, age);
  }
}
```

### Replace Derived Variable with Query

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceDerivedVariableWithQuery.html).

```ts
// Before
class Order {
  items: number[];

  constructor(items: number[]) {
    this.items = items;
  }

  getTotal(): number {
    let total = 0;
    for (const item of this.items) {
      total += item;
    }
    return total;
  }
}

// After
class Order {
  items: number[];

  constructor(items: number[]) {
    this.items = items;
  }

  getTotal(): number {
    return this.items.reduce((sum, item) => sum + item, 0);
  }
}
```

### Replace Function with Command

**Aliases**: _Replace Method with Method Object_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceFunctionWithCommand.html).

```ts
// Before
class Light {
  isOn: boolean;

  constructor() {
    this.isOn = false;
  }

  turnOn(): void {
    this.isOn = true;
  }

  turnOff(): void {
    this.isOn = false;
  }
}

// After
class Light {
  isOn: boolean;

  constructor() {
    this.isOn = false;
  }

  commandOn(): LightCommand {
    return new TurnOnCommand(this);
  }

  commandOff(): LightCommand {
    return new TurnOffCommand(this);
  }
}

interface LightCommand {
  execute(): void;
}

class TurnOnCommand implements LightCommand {
  constructor(private light: Light) { }

  execute(): void {
    this.light.isOn = true;
  }
}

class TurnOffCommand implements LightCommand {
  constructor(private light: Light) { }

  execute(): void {
    this.light.isOn = false;
  }
}
```

### Replace Inline Code with Function Call

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceConstructorWithFactoryFunction.html).

```ts
// Before
function calculateTotal(price: number, quantity: number): number {
  const taxRate = 0.1;
  return price * quantity * (1 + taxRate);
}

// After
function calculateTotal(price: number, quantity: number): number {
  return applyTax(price * quantity);
}

function applyTax(amount: number): number {
  const taxRate = 0.1;
  return amount * (1 + taxRate);
}
```

### Replace Loop with Pipeline

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceLoopWithPipeline.html).

```ts
// Before
function getDiscountedPrices(products: Product[]): number[] {
  const discountedPrices: number[] = [];
  for (const product of products) {
    const discount = calculateDiscount(product);
    discountedPrices.push(product.price * (1 - discount));
  }
  return discountedPrices;
}

// After
function getDiscountedPrices(products: Product[]): number[] {
  return products.map(product => product.calculateDiscountedPrice());
}

class Product {
  constructor(public price: number) { }

  calculateDiscountedPrice(): number {
    const discount = calculateDiscount(this);
    return this.price * (1 - discount);
  }
}
```

### Replace Nested Conditional with Guard Clauses

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceNestedConditionalWithGuardClauses.html).

```ts
// Before
function calculatePrice(product: Product): number {
  let price = product.basePrice;
  if (product.isPromoEligible()) {
    if (product.isPremium()) {
      price *= 0.9;
    } else {
      price *= 0.95;
    }
  }
  return price;
}

// After
function calculatePrice(product: Product): number {
  if (!product.isPromoEligible()) {
    return product.basePrice;
  }
  if (product.isPremium()) {
    return product.basePrice * 0.9;
  }
  return product.basePrice * 0.95;
}
```

### Replace Parameter with Query

**Aliases**: _Replace Parameter with Method_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceParameterWithQuery.html).

```ts
// Before
function calculateTotalPrice(price: number, quantity: number): number {
  return price * quantity;
}

// After
function calculateTotalPrice(product: Product): number {
  return product.getPrice() * product.getQuantity();
}
```

### Replace Primitive with Object

**Aliases**: _Replace Data Value with Object; Replace Type Code with Class_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replacePrimitiveWithObject.html).

```ts
// Before
function calculateTotalPrice(price: number, quantity: number): number {
  return price * quantity;
}

// After
class Quantity {
  constructor(private value: number) { }

  multiply(price: number): number {
    return this.value * price;
  }
}

const totalPrice = new Quantity(quantity).multiply(price);
```

### Replace Query with Parameter

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceQueryWithParameter.html).

```ts
// Before
function isDiscountEligible(orderTotal: number): boolean {
  return orderTotal > 100;
}

function calculateTotal(orderTotal: number, discountRate: number): number {
  if (isDiscountEligible(orderTotal)) {
    return orderTotal * (1 - discountRate);
  }
  return orderTotal;
}

// After
function calculateTotal(orderTotal: number, discountRate: number, isDiscountEligible: boolean): number {
  if (isDiscountEligible) {
    return orderTotal * (1 - discountRate);
  }
  return orderTotal;
}
```

### Replace Subclass with Delegate

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceSubclassWithDelegate.html).

```ts
// Before
class TeamLead extends Employee {
  // ...
}

class Employee {
  teamLead: TeamLead;

  getTeamLead(): TeamLead {
    return this.teamLead;
  }
}

// After
class Employee {
  delegate: TeamLeadDelegate;

  getTeamLead(): TeamLeadDelegate {
    return this.delegate;
  }
}

class TeamLeadDelegate {
  // ...
}
```

### Replace Superclass with Delegate

**Aliases**: _Replace Inheritance with Delegation_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceSuperclassWithDelegate.html).

```ts
// Before
class Circle extends Shape {
  radius: number;

  constructor(radius: number) {
    super();
    this.radius = radius;
  }

  // ...
}

// After
class CircleDelegate {
  shape: Shape;

  constructor(shape: Shape) {
    this.shape = shape;
  }

  getRadius(): number {
    // Return the radius using the shape data
  }

  // ...
}
```

### Replace Temp with Query

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceTempWithQuery.html).

```ts
// Before
function calculateTotalPrice(price: number, quantity: number): number {
  const totalPrice = price * quantity;
  return totalPrice > 1000 ? totalPrice * 0.9 : totalPrice;
}

// After
function calculateTotalPrice(price: number, quantity: number): number {
  return (price * quantity) > 1000 ? price * quantity * 0.9 : price * quantity;
}
```

### Replace Type Code with Subclasses

**Aliases**: _Extract Subclass; Replace Type Code with State/Strategy_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceTypeCodeWithSubclasses.html).

```ts
// Before
class Employee {
  type: string;

  constructor(type: string) {
    this.type = type;
  }
}

// After
abstract class Employee {
  abstract calculatePay(): number;
}

class FullTimeEmployee extends Employee {
  calculatePay(): number {
    // Calculation for full-time employee
  }
}

class PartTimeEmployee extends Employee {
  calculatePay(): number {
    // Calculation for part-time employee
  }
}
```

### Separate Query from Modifier

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/separateQueryFromModifier.html).

```ts
// Before
class Account {
  balance: number;

  withdraw(amount: number): void {
    if (amount > this.balance) {
      throw new Error("Insufficient balance");
    }
    this.balance -= amount;
  }
}

// After
class Account {
  balance: number;

  canWithdraw(amount: number): boolean {
    return amount <= this.balance;
  }

  withdraw(amount: number): void {
    if (!this.canWithdraw(amount)) {
      throw new Error("Insufficient balance");
    }
    this.balance -= amount;
  }
}
```

### Slide Statements

**Aliases**: _Consolidate Duplicate Conditional Fragments_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/slideStatements.html).

```ts
// Before
let discount: number = 0;
if (order.total > 100) {
  discount = 0.1;
}

// After
if (order.total > 100) {
  let discount: number = 0.1;
}
```

### Split Loop

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/splitLoop.html).

```ts
// Before
function calculateTotalPrice(cart: Cart[]): number {
  let total = 0;
  for (const item of cart) {
    total += item.price;
  }
  for (const item of cart) {
    total -= item.discount;
  }
  return total;
}

// After
function calculateTotalPrice(cart: Cart[]): number {
  let totalPrice = 0;
  for (const item of cart) {
    totalPrice += item.price;
  }

  let totalDiscount = 0;
  for (const item of cart) {
    totalDiscount += item.discount;
  }

  return totalPrice - totalDiscount;
}
```

### Split Phase

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/splitPhase.html).

```ts
// Before
function processOrder(order: Order): void {
  validateOrder(order);
  updateInventory(order);
  createInvoice(order);
}

// After
function processOrder(order: Order): void {
  validateOrder(order);
  updateInventory(order);
}

function updateInventory(order: Order): void {
  // ...
}

function createInvoice(order: Order): void {
  // ...
}
```

### Split Variable

**Aliases**: _Remove Assignments to Parameters; Split Temp_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/splitVariable.html).

```ts
// Before
let fullName: string = `${user.firstName} ${user.lastName}`;

// After
let firstName: string = user.firstName;
let lastName: string = user.lastName;
```

### Substitute Algorithm

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/substituteAlgorithm.html).

```ts
// Before
function foundPerson(people: string[]): string {
  for (const person of people) {
    if (person === "Don") {
      return "Don";
    }
    if (person === "John") {
      return "John";
    }
    if (person === "Kent") {
      return "Kent";
    }
  }
  return "";
}

// After
function foundPerson(people: string[]): string {
  const candidates = ["Don", "John", "Kent"];
  for (const person of people) {
    if (candidates.includes(person)) {
      return person;
    }
  }
  return "";
}
```

## Refactorings not in the 2nd editions

### Replace Control Flag with Break

**Aliases**: _Remove Control Flag_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceControlFlagWithBreak.html).

```ts
// Before
function findValue(arr: number[], target: number): boolean {
  let found = false;
  for (const item of arr) {
    if (item === target) {
      found = true;
      break;
    }
  }
  return found;
}

// After
function findValue(arr: number[], target: number): boolean {
  for (const item of arr) {
    if (item === target) {
      return true;
    }
  }
  return false;
}
```

### Replace Error Code with Exception

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceErrorCodeWithException.html).

```ts
// Before
function divide(a: number, b: number): number {
  if (b === 0) {
    return -1; // Error code for division by zero
  }
  return a / b;
}

// After
function divide(a: number, b: number): number {
  if (b === 0) {
    throw new Error("Division by zero");
  }
  return a / b;
}
```

### Replace Exception with Precheck

**Aliases**: _Replace Exception with Test_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceExceptionWithPrecheck.html).

```ts
// Before
function calculateDiscountedPrice(price: number, discount: number): number {
  try {
    if (discount < 0 || discount > 1) {
      throw new Error("Invalid discount");
    }
    return price * (1 - discount);
  } catch (error) {
    console.error(error);
    return price;
  }
}

// After
function calculateDiscountedPrice(price: number, discount: number): number {
  if (discount < 0 || discount > 1) {
    console.error("Invalid discount");
    return price;
  }
  return price * (1 - discount);
}
```

### Replace Magic Literal

**Aliases**: _Replace Magic Number with Symbolic Constant_.

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/replaceMagicLiteral.html).

```ts
// Before
function calculateTotal(price: number, quantity: number): number {
  return price * quantity * 1.1; // 1.1 is the tax rate
}

// After
const TAX_RATE = 1.1;

function calculateTotal(price: number, quantity: number): number {
  return price * quantity * TAX_RATE;
}
```

### Return Modified Value

🔗 In the [Refactoring catalog](https://refactoring.com/catalog/returnModifiedValue.html).

```ts
// Before
function modifyValue(value: number): number {
  value *= 2;
  value += 10;
  return value;
}

// After
function modifyValue(value: number): void {
  value *= 2;
  value += 10;
}
```
