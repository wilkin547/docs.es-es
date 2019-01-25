---
title: Referencia de palabras clave
description: Encuentre vínculos a información acerca de todos los F# palabras clave del lenguaje.
ms.date: 05/16/2016
ms.openlocfilehash: 5a94a30ca0f73538cc22e76fa75bd76741b70d99
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857910"
---
# <a name="keyword-reference"></a>Referencia de palabras clave

En este tema contiene vínculos a información acerca de todos los F# palabras clave del lenguaje.

## <a name="f-keyword-table"></a>F#Tabla de la palabra clave

La tabla siguiente se muestran todos los F# palabras clave en orden alfabético, junto con descripciones breves y vínculos a temas relevantes que contienen más información.

|Palabra clave|Vínculo|Descripción|
|-------|----|-----------|
|`abstract`|[Miembros](members/index.md)<br /><br />[Clases abstractas](abstract-classes.md)|Indica un método que ya sea en el tipo en el que se declara o que es virtual y tiene una implementación predeterminada no tiene ninguna implementación.|
|`and`|[`let` enlaces](functions/let-bindings.md)<br /><br />[Registros](records.md)<br /><br />[Miembros](members/index.md)<br /><br />[Restricciones](generics/constraints.md)|Usar en mutuamente los enlaces recursivos y registros, en las declaraciones de propiedad y con varias restricciones en parámetros genéricos.|
|`as`|[Clases](classes.md)<br /><br />[Coincidencia de patrones](Pattern-Matching.md)|Se utiliza para proporcionar un nombre de objeto a objeto de clase actual. También se usa para asignar un nombre a un modelo completo en una coincidencia de patrones.|
|`assert`|[Aserciones](assertions.md)|Se usa para comprobar el código durante la depuración.|
|`base`|[Clases](classes.md)<br /><br />[Herencia](inheritance.md)|Se utiliza como el nombre del objeto de clase base.|
|`begin`|[Sintaxis detallada](verbose-syntax.md)|En la sintaxis detallada, indica el inicio de un bloque de código.|
|`class`|[Clases](classes.md)|En la sintaxis detallada, indica el inicio de una definición de clase.|
|`default`|[Miembros](members/index.md)|Indica una implementación de un método abstracto; se usa junto con una declaración de método abstracto para crear un método virtual.|
|`delegate`|[Delegados](delegates.md)|Se utiliza para declarar a un delegado.|
|`do`|[Enlaces do](functions/do-bindings.md)<br /><br />[Bucles: `for...to` Expresión](loops-for-to-expression.md)<br /><br />[Bucles: `for...in` Expresión](loops-for-in-expression.md)<br /><br />[Bucles: `while...do` Expresión](loops-while-do-expression.md)|Se utiliza en construcciones de bucle o para ejecutar código imperativo.|
|`done`|[Sintaxis detallada](verbose-syntax.md)|En la sintaxis detallada, indica el final de un bloque de código en una expresión de bucle.|
|`downcast`|[Conversiones](casting-and-conversions.md)|Se utiliza para convertir a un tipo que está más abajo en la cadena de herencia.|
|`downto`|[Bucles: `for...to` Expresión](loops-for-to-expression.md)|En un `for` expresión, utilizada para contar en orden inverso.|
|`elif`|[Expresiones condicionales: `if...then...else`](conditional-expressions-if-then-else.md)|Se utiliza en la bifurcación condicional. Una forma abreviada de `else if`.|
|`else`|[Expresiones condicionales: `if...then...else`](conditional-expressions-if-then-else.md)|Se utiliza en la bifurcación condicional.|
|`end`|[Estructuras](structures.md)<br /><br />[Uniones discriminadas](discriminated-unions.md)<br /><br />[Registros](records.md)<br /><br />[Extensiones de tipo](type-extensions.md)<br /><br />[Sintaxis detallada](verbose-syntax.md)|En las definiciones de tipos y extensiones de tipo, indica el final de una sección de las definiciones de miembros.<br /><br />En la sintaxis detallada, se utiliza para especificar el final de un bloque de código que comienza con la `begin` palabra clave.|
|`exception`|[Control de excepciones](exception-handling/index.md)<br /><br />[Tipos de excepción](exception-handling/exception-types.md)|Se utiliza para declarar un tipo de excepción.|
|`extern`|[Funciones externas](functions/external-functions.md)|Indica que un elemento de programa declarado está definido en otro archivo binario o ensamblado.|
|`false`|[Tipos primitivos](primitive-types.md)|Se utiliza como un literal booleano.|
|`finally`|[Excepciones: El `try...finally` expresión](exception-handling/the-try-finally-expression.md)|Puede usar junto con `try` para presentar un bloque de código que se ejecuta independientemente de si se produce una excepción.|
|`fixed`|[Fixed](fixed.md)|Usa un puntero "anclar" en la pila para impedir que se recopila.|
|`for`|[Bucles: `for...to` Expresión](loops-for-to-expression.md)<br /><br />[Bucles: expresión for...in](loops-for-in-expression.md)|Se utiliza en construcciones de bucle.|
|`fun`|[Expresiones lambda: `fun`Palabra clave](functions/lambda-expressions-the-fun-keyword.md)|Usar en expresiones lambda, también se conocen como funciones anónimas.|
|`function`|[Expresiones de coincidencia](match-expressions.md)<br /><br />[Expresiones lambda: La palabra clave fun](functions/lambda-expressions-the-fun-keyword.md)|Usar como una alternativa más corta para la `fun` palabra clave y un `match` expresión en una expresión lambda que tiene la coincidencia de patrones en un único argumento.|
|`global`|[Espacios de nombres](namespaces.md)|Se utiliza para hacer referencia el espacio de nombres .NET nivel superior.|
|`if`|[Expresiones condicionales: `if...then...else`](conditional-expressions-if-then-else.md)|Se utiliza en construcciones de bifurcación condicional.|
|`in`|[Bucles: expresión for...in](loops-for-in-expression.md)<br /><br />[Sintaxis detallada](verbose-syntax.md)|Usar para las expresiones de secuencia y, en la sintaxis detallada, para separar las expresiones de enlaces.|
|`inherit`|[Herencia](inheritance.md)|Se usa para especificar una clase base o interfaz base.|
|`inline`|[Funciones](functions/index.md)<br /><br />[Funciones insertadas](functions/inline-functions.md)|Se usa para indicar que una función que se debe integrar directamente en el código del llamador.|
|`interface`|[Interfaces](interfaces.md)|Se utiliza para declarar e implementar interfaces.|
|`internal`|[Control de acceso](access-control.md)|Se utiliza para especificar que un miembro es visible dentro de un ensamblado, pero no fuera de él.|
|`lazy`|[Expresiones con procesamiento diferido](lazy-computations.md)|Se usa para especificar un cálculo que se realiza solo cuando se necesita un resultado.|
|`let`|[`let` enlaces](functions/let-bindings.md)|Se utiliza para asociar o enlazar un nombre a un valor o una función.|
|`let!`|[Flujos de trabajo asincrónicos](asynchronous-workflows.md)<br /><br />[Expresiones de cálculo](computation-expressions.md)|Se usa en flujos de trabajo asincrónicos para enlazar un nombre al resultado de un cálculo asincrónico, o bien, en otras expresiones de cálculo, que se usa para enlazar un nombre a un resultado, que es del tipo de cálculo.|
|`match`|[Expresiones de coincidencia](match-expressions.md)|Utilizado para la rama comparando un valor a un patrón.|
|`match!`|[Expresiones de cálculo](computation-expressions.md#match)|Usar inserte una llamada a una coincidencia de expresión y el patrón de cálculo en su resultado.|
|`member`|[Miembros](members/index.md)|Se utiliza para declarar una propiedad o método en un tipo de objeto.|
|`module`|[Módulos](modules.md)|Se utiliza para asociar un nombre a un grupo de tipos relacionados, los valores y las funciones, para separar lógicamente de los del resto del código.|
|`mutable`|[Enlaces let](functions/let-bindings.md)|Se utiliza para declarar una variable, es decir, un valor que se puede cambiar.|
|`namespace`|[Espacios de nombres](namespaces.md)|Se utiliza para asociar un nombre a un grupo de módulos y tipos relacionados lógicamente separarlo del resto del código.|
|`new`|[Constructores](members/constructors.md)<br /><br />[Restricciones](generics/constraints.md)|Se utiliza para declarar, definir o invocar un constructor que crea o que puede crear un objeto.<br /><br />También se usa en las restricciones de parámetro genérico para indicar que un tipo debe tener un constructor determinado.|
|`not`|[Referencia de símbolos y operadores](symbol-and-operator-reference/index.md)<br /><br />[Restricciones](generics/constraints.md)|No es una palabra clave. Sin embargo, `not struct` en combinación, se utiliza como una restricción de parámetro genérico.|
|`null`|[Valores NULL](values/null-values.md)<br /><br />[Restricciones](generics/constraints.md)|Indica la ausencia de un objeto.<br /><br />También se utiliza en las restricciones de parámetro genérico.|
|`of`|[Uniones discriminadas](discriminated-unions.md)<br /><br />[Delegados](delegates.md)<br /><br />[Tipos de excepción](exception-handling/exception-types.md)|Usar uniones discriminadas para indicar el tipo de categorías de valores y, en las declaraciones de delegado y la excepción.|
|`open`|[Declaraciones de importación: `open`Palabra clave](import-declarations-the-open-keyword.md)|Se usa para que el contenido de un espacio de nombres o módulo estén disponibles sin calificación.|
|`or`|[Referencia de símbolos y operadores](symbol-and-operator-reference/index.md)<br /><br />[Restricciones](generics/constraints.md)|Usar con condiciones booleanas como un valor booleano `or` operador. Equivalente a '||`.<br /><br />También se utiliza en las restricciones de miembro.|
|`override`|[Miembros](members/index.md)|Se usa para implementar una versión de un método abstracto o virtual que difiere de la versión base.|
|`private`|[Control de acceso](access-control.md)|Restringe el acceso a un miembro al código en el mismo tipo o módulo.|
|`public`|[Control de acceso](access-control.md)|Permite el acceso a un miembro desde fuera del tipo.|
|`rec`|[Funciones](functions/index.md)|Se utiliza para indicar que una función es recursiva.|
|`return`|[Flujos de trabajo asincrónicos](Asynchronous-Workflows.md)<br /><br />[Expresiones de cálculo](computation-expressions.md)|Se utiliza para indicar un valor que se va a proporcionar como resultado de una expresión de cálculo.|
|`return!`|[Expresiones de cálculo](computation-expressions.md)<br /><br />[Flujos de trabajo asincrónicos](asynchronous-workflows.md)|Utilizado para indicar una expresión de cálculo que, cuando se evalúa, proporciona el resultado de la expresión de cálculo que contiene.|
|`select`|[Expresiones de consulta](query-expressions.md)|Se utiliza en expresiones de consulta para especificar qué campos o columnas para extraer. Tenga en cuenta que esto es una palabra clave contextual, lo que significa que no es realmente una palabra reservada y sólo actúa como una palabra clave en el contexto adecuado.|
|`static`|[Miembros](members/index.md)|Se utiliza para indicar un método o propiedad que se pueda llamar sin una instancia de un tipo o un miembro value que se comparte entre todas las instancias de un tipo.|
|`struct`|[Estructuras](structures.md)<br /><br /> [Tuplas](tuples.md)<br/><br/>[Restricciones](generics/constraints.md)|Se utiliza para declarar un tipo de estructura.<br /><br/>Se usa para especificar una tupla de struct.<br/><br />También se utiliza en las restricciones de parámetro genérico.<br /><br />Se utiliza para la compatibilidad de OCaml en las definiciones de módulo.|
|`then`|[Expresiones condicionales: `if...then...else`](conditional-expressions-if-then-else.md)<br /><br />[Constructores](members/constructors.md)|Usar en expresiones condicionales.<br /><br />También se usa para realizar efectos después de la construcción de objetos.|
|`to`|[Bucles: `for...to` Expresión](loops-for-to-expression.md)|Utilizado en `for` bucles para indicar un intervalo.|
|`true`|[Tipos primitivos](primitive-types.md)|Se utiliza como un literal booleano.|
|`try`|[Excepciones: La expresión try... with](exception-handling/the-try-with-expression.md)<br /><br />[Excepciones: Try... finally expresión](exception-handling/the-try-finally-expression.md)|Se usa para presentar un bloque de código que podría generar una excepción. Puede usar junto con `with` o `finally`.|
|`type`|[Tipos en F#](fsharp-types.md)<br /><br />[Clases](classes.md)<br /><br />[Registros](records.md)<br /><br />[Estructuras](structures.md)<br /><br />[Enumeraciones](enumerations.md)<br /><br />[Uniones discriminadas](discriminated-unions.md)<br /><br />[Abreviaturas de tipo](type-abbreviations.md)<br /><br />[Unidades de medida](units-of-measure.md)|Se utiliza para declarar una clase, registro, estructura, unión discriminada, tipo de enumeración, unidad de medida o la abreviatura de tipo.|
|`upcast`|[Conversiones](casting-and-conversions.md)|Se utiliza para convertir a un tipo que es más alto en la cadena de herencia.|
|`use`|[Administración de recursos: `use`Palabra clave](resource-management-the-use-keyword.md)|Utilizar en lugar de `let` para los valores que requieren `Dispose` llamarse para liberar recursos.|
|`use!`|[Expresiones de cálculo](computation-expressions.md)<br /><br />[Flujos de trabajo asincrónicos](asynchronous-workflows.md)|Utilizar en lugar de `let!` en flujos de trabajo asincrónicos y otras expresiones de cálculo para los valores que requieren `Dispose` llamarse para liberar recursos.|
|`val`|[Campos explícitos: `val`Palabra clave](members/explicit-fields-the-val-keyword.md)<br /><br />[Firmas](signatures.md)<br /><br />[Miembros](members/index.md)|Utilizar en una firma para indicar un valor, o en un tipo para declarar a un miembro, en situaciones muy concretas.|
|`void`|[Tipos primitivos](primitive-types.md)|Indica el .NET `void` tipo. Se usa al interoperar con otros lenguajes. NET.|
|`when`|[Restricciones](generics/constraints.md)|Utilizado para las condiciones booleanas (*cuando protege*) en las coincidencias de patrón e introducir una cláusula de restricción para un parámetro de tipo genérico.|
|`while`|[Bucles: `while...do` Expresión](loops-while-do-expression.md)|Presenta una construcción de bucle.|
|`with`|[Expresiones de coincidencia](match-expressions.md)<br /><br />[Expresiones de objeto](object-expressions.md)<br /><br />[Expresiones de registro de copia y actualización](copy-and-update-record-expressions.md)<br /><br />[Extensiones de tipo](type-extensions.md)<br /><br />[Excepciones: El `try...with` expresión](exception-handling/the-try-with-expression.md)|Puede usar junto con el `match` palabra clave en las expresiones de coincidencia de patrones. También se utiliza en expresiones de objeto, expresiones de copia de registros y las extensiones de tipo para introducir las definiciones de miembros e introducir a controladores de excepciones.|
|`yield`|[Secuencias](sequences.md)|Se utiliza en una expresión de secuencia para generar un valor para una secuencia.|
|`yield!`|[Expresiones de cálculo](computation-expressions.md)<br /><br />[Flujos de trabajo asincrónicos](asynchronous-workflows.md)|Se usa en una expresión de cálculo para anexar el resultado de una expresión de cálculo determinado a una colección de los resultados de la expresión de cálculo que contiene.|

Los tokens siguientes están reservados en F# porque son palabras clave en el lenguaje OCaml:

* `asr`
* `land`
* `lor`
* `lsl`
* `lsr`
* `lxor`
* `mod`
* `sig`

Si usas el `--mlcompatibility` opción del compilador, las palabras clave anteriores están disponibles para su uso como identificadores.

Los tokens siguientes están reservados como palabras clave para una futura ampliación de la F# idioma:

* `atomic`
* `break`
* `checked`
* `component`
* `const`
* `constraint`
* `constructor`
* `continue`
* `eager`
* `event`
* `external`
* `functor`
* `include`
* `method`
* `mixin`
* `object`
* `parallel`
* `process`
* `protected`
* `pure`
* `sealed`
* `tailcall`
* `trait`
* `virtual`
* `volatile`

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Referencia de símbolos y operadores](symbol-and-operator-reference/index.md)
- [Opciones del compilador](compiler-options.md)
