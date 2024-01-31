# null和undefined区别
The difference between null and undefined

First of all, Undefined and Null are both basic data types. Each of these two basic data types has only one value, which is undefined and null.

undefined 代表的含义是未定义，null 代表的含义是空对象。一般变量声明了但还没有定义的时候会返回 undefined，null主要用于赋值给一些可能会返回对象的变量，作为初始化。
Undefined means undefined, while null means empty object. When a general variable is declared but not yet defined, it will return undefined. null is mainly used to assign values to variables that may return objects as initialization.

undefined 在 JavaScript 中不是一个保留字，这意味着可以使用 undefined 来作为一个变量名，但是这样的做法是非常危险的，它会影响对 undefined 值的判断。我们可以通过一些方法获得安全的 undefined 值，比如说 void 0。
Undefined is not a reserved word in JavaScript, which means that it can be used as a variable name, but this approach is very dangerous as it can affect the judgment of the undefined value. We can obtain secure undefined values through some methods, such as void 0.

当对这两种类型使用 typeof 进行判断时，Null 类型化会返回 “object”，这是一个历史遗留的问题。当使用双等号对两种类型的值进行比较时会返回 true，使用三个等号时会返回 false。
When using typeof to judge these two types, Null typing will return "object", which is a historical problem. Returns true when using a double equal sign to compare two types of values, and returns false when using a triple equal sign.