# RolLangTodoList

## Testing
* Circular check for subtypes.
* Circular check for function constrain check (after adding nested function constrain check in constrain).
* Generic types and functions with ```REF_EMPTY```.
* Virtual function type check.
* Backtracking of sub-traits (multiple levels).
* Check the use of ```additionalUd``` in ```LoadTraitFunctionCacheInfo```.
* Redirect field, constant, trait.
* ```REF_CONSTRAIN``` for function, virtual function (v/i), field.

## Loader constrain module
* Rename "constrain" to "constraint". (too late?)
* Constrains of member functions not checked when matching overloads.
  * Create ```CTT_ANY``` for ```REF_CONSTRAIN``` types.
  * Match parameter types and return type.
  * Apply equal to the ```CTT_ANY``` with corresponding exported types.
* ```REF_CONSTRAIN``` not supported in constrain module.
  * ```REF_CONSTRAIN``` of trait: should throw.
  * ```REF_CONSTRAIN``` of determined type: should calculate.
  * ```REF_CONSTRAIN``` of function overloads: see constrain check of overloads.
* Generic member function. (Separate list. Should match exactly, no type deduction.)
* Deduction of ```REF_EMPTY```.
* Use separate function to export components.
* More components to export (```REF_ANY``` arguments).
* Move sub-trait tests to the last to check (fail fast).
* Function overload matching weighting (generic, vtab/itab).
* Directly call ```TryCalculateTraitSubMember``` instead of using one separate determining pass.
* Avoid name conflict for ```ConstrainType```.

## Loader core module
* Check support for ```REF_EMPTY```.
* Set ```_loading``` to null after loading.
* Circular check for ```EnsureFunctionLoaded```.
* Finalizer should allow ref embed.
* Should check exact matching for imported generic objects.

## Loader reflist module
* Resolve ```REF_CLONE``` and circular check.
* Move helper function to count ```REF_ARGUMENT``` from constrain module.
  * Fix the incorrect implementation for ```REF_ASSEMBLY``` and ```REF_IMPORT```.
* Helper function to build ref type description (given a builder type as generic argument).
* Auto redirect by subtype (for specific language frontend feature).

## Loader common
* Use new container class for parent type (constrain type and builder type).
* Helper function to compare ```MultiList``` (constrain type).
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
  * Constrain type deduction.
  * Parameter.
  * Field.
* Partial specialization (type overload).
  * Variable-sized object.
  * Attribute.
