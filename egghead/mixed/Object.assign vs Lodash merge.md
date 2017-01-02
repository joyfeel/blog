# 《Object.assign vs Lodash merge》
合併 object 時, 最基本就是直接用 Object.assign。但若 nested objects 超過2層的話, 則用_.merge
```javascript
const defaultOptions = {
  amount: 10,
  quantity: 1,
  color: 'maroon',
  material: 'cotton',
  sizes: {
    small: true,
    medium: true,
    large: true
  }
};

function inventory(userOptions) {
  console.log(Object.assign({}, defaultOptions, userOptions));
  console.log(_.merge({}, defaultOptions, userOptions));
};

inventory({
  amount: 15,
  quantity: 6,
  material: 'wool',
  sizes: {
    extraLarge: true
  }
});
```

Ref: https://egghead.io/lessons/javascript-combine-objects-with-object-assign-and-lodash-merge
