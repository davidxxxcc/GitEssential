# Module Pattern in JavaScript

## Model View Controller \(MVC\)

* ### Model: data module
* ### View: UI module
* ### Controller: controller module

### ![](/assets/js-25)![](/assets/js-29)1. Setup three IIFEs

![](/assets/js-31)

### 2. Data model build up in `budgetgetController `

Let's set up a constructor `Expense`and `Income` and its prototype method to define every record.

`data `object collect all types of data including `exp[] `and `inc[]`.

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
};

// Income contructor
var Income = function(id, description, value) {
    this.id = id;
    this.description = description;
    this.value = value;
};

//Data object
var data = {
    allItems: {
        exp:[],
        inc:[]
    },
    totals: {
        exp: 0,
        inc: 0
    },
    budget: 0,
    percentage: -1
};

var calculateTotal = function(type) {
    var sum = 0;
    data.allItems[type].forEach(function(cur) {
       sum += cur.value; 
    });
    data.totals[type] = sum;
};
    
```

### 3. Public methods build up in `budgetgetController `



### Demo code on GitHub:

[https://github.com/davidxxxcc/BudgetyApp](https://github.com/davidxxxcc/BudgetyApp)

