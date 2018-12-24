# RolLangTodoList

## Testing
* Circular check for function constraint check (after adding nested function constraint check in constraint).
* Generic types and functions with ```REF_EMPTY```.
* Virtual function type check.
* Backtracking of sub-traits (multiple levels).
* Check the use of ```additionalUd``` in ```LoadTraitFunctionCacheInfo```.
* Redirect field, constant, trait.
* ```REF_CONSTRAINT``` for function, virtual function (v/i), field.
* Derive types in trait function overload by function constraint.
* ```REF_CONSTRAINT``` support for constraint module (determined types, functions, traits).

## Loader constraint module
* Generic member function. (Separate list. Should match exactly, no type deduction.)
* Deduction of ```REF_EMPTY```.
* Use separate function to export components.
* More components to export (```REF_ANY``` arguments).
* Move sub-trait tests to the last to check (fail fast).
* Function overload matching weighting (generic, vtab/itab).
* Directly call ```TryCalculateTraitSubMember``` instead of using one separate determining pass.
* Avoid name conflict for ```ConstraintType```.

## Loader core module
* Circular check for ```EnsureFunctionLoaded```.
* Finalizer should allow ref embed.
* Should check exact matching for imported generic objects.

## Loader reflist module
* Resolve ```REF_CLONE``` and circular check.
* Move helper function to count ```REF_ARGUMENT``` from constraint module.
* Helper function to build ref type description (given a builder type as generic argument).
* Auto redirect by subtype (for specific language frontend feature).

## Loader common
* Use new container class for parent type (constraint type and builder type).
* Helper function to compare ```MultiList``` (constraint type).
* ```CopyList``` change to iterator.
* Allow ```GetRefArgList``` without target.
* Make functions to be static whenever possible.
* Support more necessary stages for loading limit check.

## Interpreter
* Instructions for referencing fields and functions.
* Analysis of stack layout.

## Features not implemented
* Parameter pack.
  * Argument list segment support.
  * Variable size segment.
  * Reference list expanding support.
  * Reference list expanding level control.
  * Constraint type deduction.
  * Parameter.
  * Field.
* Partial specialization (type overload).
  * Variable-sized object.
  * Attribute.
