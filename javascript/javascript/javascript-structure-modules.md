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
var formatNumber = function(num, type) {
        //some code
};

return {
        getInput: function() {
            return {
                type : document.querySelector(DOMstrings.inputType).value,  //Will be either inc or exp
                description : document.querySelector(DOMstrings.inputDescription).value,
                value : parseFloat(document.querySelector(DOMstrings.inputValue).value)
            };
        },
        addListItem: function(obj, type) {
                //some code
        },
        deleteListItem: function(selectorID) {
                //some code
        },


}
```

### 5. Global controller in `controller`

We can use the parameter from `budgetController`& `UIController`as long as we pass these functions to `controller`module. We use `UICtrl`and `budgetCtrl` to represent these two functions. We define the controller module inculding event lister, update the budget, update percentage, controll adding & deleting item and initialize the application.

```
var setupEventListeners = function() {
    var DOM = UICtrl.getDOMstrings();
    document.querySelector(DOM.inputBtn).addEventListener('click', ctrlAddItem);
    document.addEventListener('keypress', function(event){
        if(event.keyCode === 13 || event.which === 13) {
            ctrlAddItem();
        }
    });
    document.querySelector(DOM.container).addEventListener('click', ctrlDeleteItem);
    document.querySelector(DOM.inputType).addEventListener('change',UICtrl.changedType);
};

var updatePercentages = function() {

    // 1. Calculate percentages
    budgetCtrl.calculatePercentages();

    // 2. Read percentages from the budget controller
    var percentages = budgetCtrl.getPercentage();
    console.log(percentages);

    // .3 Update the UI with the new percentages
    UICtrl.displayPercentages(percentages);    
};

var ctrlAddItem = function() {
    var input, newItem;

    // 1. Get the fieled input data
    input = UICtrl.getInput();
    if(input.description !== "" && !isNaN(input.value) && input.value > 0){

        // 2. Add the item to the budget controller
        newItem = budgetCtrl.addItem(input.type, input.description, input.value);

        // 3. Add the item to the UI
        UICtrl.addListItem(newItem, input.type);

        // 4. Clear the fields
        UICtrl.clearFields();

        // 5. calculate and update budget
        updateBudget();

        // 6. Calculate and update percentages
        updatePercentages();
    }
};

 return {
        init: function() {
            console.log('Applicaation has started.');
            UICtrl.displayMonth();
            UICtrl.displayBudget({
                budget: 0,
                totalInc: 0,
                totalExp: 0,
                percentage: -1
            });
            setupEventListeners();
        }
}
```

### Demo code on GitHub:

[https://github.com/davidxxxcc/BudgetyApp](https://github.com/davidxxxcc/BudgetyApp)

