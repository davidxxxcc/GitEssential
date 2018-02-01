# Module Pattern in JavaScript

## Model View Controller \(MVC\)

* ### Model: data module
* ### View: UI module
* ### Controller: controller module

### ![](/assets/js-25)![](/assets/js-29)1. Setup three IIFEs

![](/assets/js-31)

### 2. Data model build up in `budgetgetController`

Let's set up a constructor `Expense`and `Income` and its prototype method to define every record.

`data`object collect all types of data including `exp[]`and `inc[]`.

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

### 3. Public methods build up in `budgetgetController`

We can define any public method in `return`scope so that other outside function can access.

```
return {
    addItem: function(type, des, val) {
        //some code
        //Create new item based on 'inc' or 'exp' type
        if (type === 'exp') {
            newItem = new Expense(ID, des, val);
        } else if (type === 'inc') {
            newItem = new Income(ID, des, val);
        }
         //Push it into our data structure
        data.allItems[type].push(newItem);
        //Reutrn the new element
        return newItem;

    },
    deleteItem: function(type, id) {
        //some code
    },

    calculateBudget: function() {
       //some code
    },
    .
    .
    .
}
```

### 4. UI variable in method in `UIController`

We can define the DOM as a object.

```
var DOMstrings = {
        inputType: '.add__type',
        inputDescription: '.add__description',
        inputValue: '.add__value',
        inputBtn: '.add__btn',
        incomeContainer: '.income__list',
        expensesContainer: '.expenses__list',
        budgetLabel: '.budget__value',
        incomeLabel: '.budget__income--value',
        expensesLabel: '.budget__expenses--value',
        percentageLabel: '.budget__expenses--percentage',
        container: '.container',
        expensesPercLabel: '.item__percentage',
        dateLabel: '.budget__title--month'
        
    };
    
    
```

### Demo code on GitHub:

[https://github.com/davidxxxcc/BudgetyApp](https://github.com/davidxxxcc/BudgetyApp)

