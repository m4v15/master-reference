# Object Cloning

In the code:
```
var mondayFood = {breakfast: 'porridge', lunch: 'pizza', dinner: 'paella'};
var tuesdayFood = mondayFood;
```
'tuesdayFood' is not an object itself, but an instruction that points towards 'mondayFood'. If you try and change something in 'tuesdayFood', what you're actually doing is directing the code to 'mondayFood'. 
So the instruction `tuesdayFood.lunch = 'pasta';` would actually mean:

> 'Look up the thing 'tuesdayFood' is referencing, and change the 'lunch' property.' 

And because 'tuesdayFood' is a reference to 'mondayFood', you'll end up changing 'mondayFood' - specifically, 'mondayFood.lunch'. And you'd miss out on your pizza: 
```
var mondayFood = {breakfast: 'porridge', lunch: 'pizza', dinner: 'paella'};
var tuesdayFood = mondayFood;

tuesdayFood.lunch = 'pasta';
console.log(mondayFood); // {breakfast: 'porridge', lunch: 'pasta', dinner: 'paella'}
console.log(tuesdayFood); // {breakfast: 'porridge', lunch: 'pasta', dinner: 'paella'}
```

If you want to make a clone of the object, you can use JSON.parse(JSON.stringify(...)); 
```
var tuesdayFood = JSON.parse(JSON.stringify(mondayFood));
```
Now, 'tuesdayFood' refers to a separate object than 'mondayFood' (at the moment, they are separate and identical). So this time, when you try and change 'tuesdayFood', the execution goes nowhere near 'mondayFood'. So, this time, changing 'tuesdayFood.lunch' changes the new tuesdayFood object, and not the existing mondayFood one. 
```
var mondayFood = {breakfast: 'porridge', lunch: 'pizza', dinner: 'paella'};
var tuesdayFood = JSON.parse(JSON.stringify(mondayFood));

tuesdayFood.lunch = 'pasta';
console.log(mondayFood); // {breakfast: 'porridge', lunch: 'pizza', dinner: 'paella'}
console.log(tuesdayFood); // {breakfast: 'porridge', lunch: 'pasta', dinner: 'paella'}
```

`JSON.parse(JSON.stringify(...))` is a bit hacky, and when you're using ES6, you'll find out about Object.assign()...
