# Module Pattern in JavaScript

## Model View Controller \(MVC\)

* ### Model: data module
* ### View: UI module
* ### Controller: controller module

### ![](/assets/js-25)![](/assets/js-29)1. Setup three IIFEs

![](/assets/js-31)

### 2. Data model build up

Let's set up a constructor `Expense`and `Income`to define every record.

```
// Expense contructor
var Expense = function(id, description, value) {
    this.id = id;
    this.description = description;
    this.value = value;
    this.percentage = -1;
};

Expense.prototype.calcPercentage = function(totalIncome) {
    if(totalIncome > 0) {
        this.percentage = Math.round((this.value/ totalIncome) * 100);
    } else {
        this.percentage = -1;
    }
};

Expense.prototype.getPercentage = function() {
return this.percentage;

// Income contructor
var Income = function(id, description, value) {
    this.id = id;
    this.description = description;
    this.value = value;
};

}
```

## 

### Demo code on GitHub:

[https://github.com/davidxxxcc/BudgetyApp](https://github.com/davidxxxcc/BudgetyApp)

