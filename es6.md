# ES6 io.js-ზე

io.js აწყობილია უახლეს [V8](https://code.google.com/p/v8/)-თან ერთად. io.js ყოველთვის შეიცავს ამ ძრავის ბოლო განახლებებს, რომელიც დეველოპერებისთვის პერიოდულად გვაძლევს უახლეს შესაძლებლობებს [JavaScript ECMA-262 specification](http://www.ecma-international.org/publications/standards/Ecma-262.htm)-დან სისწრაფისა და სტაბილურობის ჩათვლით.

io.js ვერსია {{project.current_version}} შეიცავს V8 {{project.current_v8}}, რომელიც მოიცავს ES6 თავისებურებებს. ეს ვერსია გაცილებით წინაა ვერსია 3.28.73-თან შედარებით, რომელიც მოყვება Node.js™ 0.12.x-ს.

## უკვე --harmony ალამის გარეშე

Node.js™@0.12.x (V8 3.28+) ვერსიაში, `--harmony` ალამი რთავს ყველა **დამთავრებულ**, **staged** and **პროგრესში მყოფ** ES6 შესაძლებლობებს ერთდროულად (გამონაკლისია `proxies` რომელიც დამალულია `--harmony-proxies` ალამის მიღმა). ეს ნიშნავს, რომ ზოგიერთი არასტაბილური იმპლემენტაცია, მაგალითისთვის [Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) ისევე ხელმისაწვდომია დეველოპერებისთვის როგორც [Generator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*)-ები, რომლებსაც გაცილებით დიდი სტაბილურობა გააჩნია. ამის გამო, უმეტესი დეველოპერები მხოლოდ გარკვეულ შესაძლებლობებს რთავდნენ სხვადასხვა ალმების გამოყენებით (როგორიცაა `--harmony-generators`), ან ყველა შესაძლებლობებს და იყენებდნენ მხოლოდ ნაწილს.

io.js@1.x (V8 4.1+)-თან ამგვარი პრობლემები არ არსებობს. ყველა "ჰარმონი" შესაძლებლობა დაყოფილია 3 ლოგიკურ ჯგუფად - **shipping**, **staged** და **პროგრესში მყოფი**:

*   All **shipping** features, the ones that V8 has considered stable, like [generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*), [templates](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/template_strings), [new string methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/New_in_JavaScript/ECMAScript_6_support_in_Mozilla#Additions_to_the_String_object) and many others are turned **on by default on io.js** and do **NOT** require any kind of runtime flag.
*   Then there are **staged** features which are almost-completed features that haven't been completely tested or updated to the latest spec yet and therefore are not considered stable by the V8 team (e.g. there might be some edge cases left to discover). This is probably the equivalent of the state of [generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*) on 3.26. These are the "use at your own risk" type of features that now require a runtime flag: `--es_staging` (or its synonym, `--harmony`).
*   Finally, all **in progress** features can be activated individually by their respective harmony flag (e.g. `--harmony_arrow_functions`), although this is highly discouraged unless for testing purposes.

## Which ES6 features ship with io.js by default (no runtime flag required)?


*   Block scoping

    *   [let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)

    *   [const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)

    *   `function`-in-blocks

    >As of v8 3.31.74.1, block-scoped declarations are [intentionally implemented with a non-compliant limitation to strict mode code](https://groups.google.com/forum/#!topic/v8-users/3UXNCkAU8Es). Developers should be aware that this will change as v8 continues towards ES6 specification compliance.

*   Collections

    *   [Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)

    *   [WeakMap](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap)

    *   [Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)

    *   [WeakSet](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet)

*   [Generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*)

*   [Binary and Octal literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Numeric_literals)

*   [Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

*   [New String methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/New_in_JavaScript/ECMAScript_6_support_in_Mozilla#Additions_to_the_String_object)

*   [Symbols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol)

*   [Template strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/template_strings)

You can view a more detailed list, including a comparison with other engines, on the [compat-table](https://kangax.github.io/compat-table/es6/) project page.

## Which ES6 features are behind the --es_staging flag?

*   [Classes](https://github.com/lukehoban/es6features#classes) (strict mode only, behind flag `--harmony_classes` which implies block scoping & object literal extensions)

*   [Object literal extensions](https://github.com/lukehoban/es6features#enhanced-object-literals) (behind flag `--harmony_object_literals`)

*   [`Symbol.toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol) (user-definable results for `Object.prototype.toString`, behind flag `--harmony_tostring`)

## Which ES6 features are in progress?

New features are constantly being added to the V8 engine. Generally speaking, expect them to land on a future io.js release, although timing is unknown.

You may list all the *in progress* features available on each io.js release by grepping through the `--v8-options` argument. Please note that these are incomplete and possibly broken features of V8, so use them at your own risk:

```sh
iojs --v8-options | grep "in progress"
```

## I have my infrastructure set up to leverage the --harmony flag. Should I remove it?

The current behaviour of the `--harmony` flag on io.js is to enable **staged** features only. After all, it is now a synonym of `--es_staging`. As mentioned above, these are completed features that have not been considered stable yet. If you want to play safe, especially on production environments, consider removing this runtime flag until it ships by default on V8 and, consequently, on io.js. If you keep this enabled, you should be prepared for further io.js upgrades to break your code if V8 changes their semantics to more closely follow the standard.

## How do I find which version of V8 ships with a particular version of io.js?

io.js provides a simple way to list all dependencies and respective versions that ship with a specific binary through the `process` global object. In case of the V8 engine, type the following in your terminal to retrieve its version:

```sh
iojs -p process.versions.v8
```
