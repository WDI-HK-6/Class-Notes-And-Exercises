#Programmatically Create Object Keys and Values in JavaScript

```javascript
// This is what you want, but you want 'categoryVoted.category1' and 'userId' to be derived from variables
update({_id: 'id1'}, {$addToSet: {'categoryVoted.category1': 'userId'}});

// This creates everything, including $addToSet
var returnAddToSetObject = function(category, userId){
  var key = 'categoryVoted.' + category;
  var object = {};
  object.$addToSet = {};
  object.$addToSet[key] = userId;
  return object;
};

// This is how you run it
update({_id: 'id'}, returnAddToSetObject('category3', 'HIhews8fy7ufw'));

// This creates only the object that is the *value* of the $addToSet *key*
var returnCategoryVotedObject = function(category, userId){
  var key = 'categoryVoted.' + category;
  var object = {};
  object[key] = userId;
  return object;
};

// This is how you run it
update({_id: 'id1'}, {$addToSet: returnAddToSetObject('category3', 'HIhews8fy7ufw')});
```