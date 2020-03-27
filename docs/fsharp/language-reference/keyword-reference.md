---
title: Referencia de palabras clave
description: Encuentre vínculos a información sobre todas las palabras clave del lenguaje F.
f1_keywords:
- new_FS
- use_FS
- end_FS
- lsl_FS
- exception_FS
- asr_FS
- if_FS
- internal_FS
- default_FS
- in_FS
- lsr_FS
- open_FS
- static_FS
- assert_FS
- match_FS
- land_FS
- with_FS
- inherit_FS
- mutable_FS
- downto_FS
- false_FS
- sig_FS
- and_FS
- true_FS
- namespace_FS
- public_FS
- lxor_FS
- val_FS
- void_FS
- downcast_FS
- function_FS
- while_FS
- for_FS
- class_FS
- done_FS
- to_FS
- module_FS
- let_FS
- delegate_FS
- abstract_FS
- then_FS
- when_FS
- lazy_FS
- try_FS
- inline_FS
- do_FS
- upcast_FS
- begin_FS
- base_FS
- fun_FS
- struct_FS
- as_FS
- extern_FS
- null_FS
- lor_FS
- return_FS
- mod_FS
- private_FS
- of_FS
- or_FS
- member_FS
- type_FS
- rec_FS
- elif_FS
- override_FS
- interface_FS
- yield_FS
- else_FS
- finally_FS
- global_FS
- select_FS
- use!_FS
dev_langs:
- FSharp
ms.date: 11/04/2019
ms.openlocfilehash: 34959f471406643e85990c2c80a38a684759a7f9
ms.sourcegitcommit: b16eacb6f94a5b601882a861ad17cc5470a8d5d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80352309"
---
# <a name="keyword-reference"></a>Referencia de palabras clave

En este tema se proporcionan vínculos a información acerca de todas las palabras clave del lenguaje F.

## <a name="f-keyword-table"></a>Tabla de palabras clave de F

En la tabla siguiente se muestran todas las palabras clave de F en orden alfabético, junto con breves descripciones y vínculos a temas relevantes que contienen más información.

|Palabra clave|Vínculo|Descripción|
|-------|----|-----------|
|`abstract`|[Miembros](./members/index.md)<br /><br />[Clases abstractas](abstract-classes.md)|Indica un método que no tiene ninguna implementación en el tipo en el que se declara o que es virtual y tiene una implementación predeterminada.|
|`and`|[`let`Enlaces](./functions/let-bindings.md)<br /><br />[Registros](records.md)<br /><br />[Miembros](./members/index.md)<br /><br />[Restricciones](./generics/constraints.md)|Se utiliza en enlaces y registros mutuamente recursivos, en declaraciones de propiedad y con varias restricciones en parámetros genéricos.|
|`as`|[Clases](classes.md)<br /><br />[Coincidencia de modelos](Pattern-Matching.md)|Se utiliza para asignar al objeto de clase actual un nombre de objeto. También se utiliza para dar un nombre a un patrón completo dentro de una coincidencia de patrón.|
|`assert`|[Aserciones](assertions.md)|Se utiliza para comprobar el código durante la depuración.|
|`base`|[Clases](classes.md)<br /><br />[Herencia](inheritance.md)|Se utiliza como el nombre del objeto de clase base.|
|`begin`|[Sintaxis detallada](verbose-syntax.md)|En la sintaxis detallada, indica el inicio de un bloque de código.|
|`class`|[Clases](classes.md)|En la sintaxis detallada, indica el inicio de una definición de clase.|
|`default`|[Miembros](./members/index.md)|Indica una implementación de un método abstracto; junto con una declaración de método abstracto para crear un método virtual.|
|`delegate`|[Delegados](delegates.md)|Se utiliza para declarar un delegado.|
|`do`|[do (Enlaces)](./functions/do-bindings.md)<br /><br />[Bucles: expresión `for...to`](loops-for-to-expression.md)<br /><br />[Bucles: expresión `for...in`](loops-for-in-expression.md)<br /><br />[Bucles: expresión `while...do`](loops-while-do-expression.md)|Se utiliza en construcciones de bucle o para ejecutar código imperativo.|
|`done`|[Sintaxis detallada](verbose-syntax.md)|En la sintaxis detallada, indica el final de un bloque de código en una expresión de bucle.|
|`downcast`|[Conversiones](casting-and-conversions.md)|Se utiliza para convertir a un tipo que es inferior en la cadena de herencia.|
|`downto`|[Bucles: expresión `for...to`](loops-for-to-expression.md)|En `for` una expresión, se utiliza al contar en sentido inverso.|
|`elif`|[Expresiones condicionales:`if...then...else`](conditional-expressions-if-then-else.md)|Se utiliza en la bifurcación condicional. Una forma `else if`corta de .|
|`else`|[Expresiones condicionales:`if...then...else`](conditional-expressions-if-then-else.md)|Se utiliza en la bifurcación condicional.|
|`end`|[Estructuras](structures.md)<br /><br />[Uniones discriminadas](discriminated-unions.md)<br /><br />[Registros](records.md)<br /><br />[Extensiones de tipo](type-extensions.md)<br /><br />[Sintaxis detallada](verbose-syntax.md)|En las definiciones de tipo y las extensiones de tipo, indica el final de una sección de definiciones de miembro.<br /><br />En la sintaxis detallada, se usa para especificar `begin` el final de un bloque de código que comienza con la palabra clave.|
|`exception`|[Control de excepciones](./exception-handling/index.md)<br /><br />[Tipos de excepción](./exception-handling/exception-types.md)|Se utiliza para declarar un tipo de excepción.|
|`extern`|[Funciones externas](./functions/external-functions.md)|Indica que un elemento de programa declarado se define en otro binario o ensamblado.|
|`false`|[Tipos primitivos](basic-types.md)|Se utiliza como literal booleano.|
|`finally`|[Excepciones: `try...finally` La expresión](./exception-handling/the-try-finally-expression.md)|Se utiliza `try` junto con para introducir un bloque de código que se ejecuta independientemente de si se produce una excepción.|
|`fixed`|[Corregido](fixed.md)|Se utiliza para "pin" un puntero en la pila para evitar que se recopile la basura.|
|`for`|[Bucles: expresión `for...to`](loops-for-to-expression.md)<br /><br />[Bucles: expresión for...in](loops-for-in-expression.md)|Se utiliza en construcciones de bucle.|
|`fun`|[Expresiones lambda: la `fun` palabra clave](./functions/lambda-expressions-the-fun-keyword.md)|Se utiliza en expresiones lambda, también conocidas como funciones anónimas.|
|`function`|[Expresiones de coincidencia](match-expressions.md)<br /><br />[Expresiones Lambda: La palabra clave divertida](./functions/lambda-expressions-the-fun-keyword.md)|Se utiliza como una `fun` alternativa más `match` corta a la palabra clave y una expresión en una expresión lambda que tiene coincidencia de patrones en un único argumento.|
|`global`|[Espacios de nombres](namespaces.md)|Se utiliza para hacer referencia al espacio de nombres de .NET de nivel superior.|
|`if`|[Expresiones condicionales:`if...then...else`](conditional-expressions-if-then-else.md)|Se utiliza en construcciones de bifurcación condicional.|
|`in`|[Bucles: expresión for...in](loops-for-in-expression.md)<br /><br />[Sintaxis detallada](verbose-syntax.md)|Se utiliza para expresiones de secuencia y, en sintaxis detallada, para separar expresiones de enlaces.|
|`inherit`|[Herencia](inheritance.md)|Se utiliza para especificar una clase base o una interfaz base.|
|`inline`|[Funciones](./functions/index.md)<br /><br />[Funciones insertadas](./functions/inline-functions.md)|Se utiliza para indicar una función que debe integrarse directamente en el código del autor de la llamada.|
|`interface`|[Interfaces](interfaces.md)|Se utiliza para declarar e implementar interfaces.|
|`internal`|[Control de acceso](access-control.md)|Se utiliza para especificar que un miembro está visible dentro de un ensamblado, pero no fuera de él.|
|`lazy`|[Expresiones diferidas](lazy-expressions.md)|Se utiliza para especificar una expresión que se va a realizar solo cuando se necesita un resultado.|
|`let`|[`let`Enlaces](./functions/let-bindings.md)|Se utiliza para asociar o enlazar un nombre a un valor o función.|
|`let!`|[Flujos de trabajo asincrónicos](asynchronous-workflows.md)<br /><br />[Expresiones de cálculo](computation-expressions.md)|Se utiliza en flujos de trabajo asincrónicos para enlazar un nombre al resultado de un cálculo asincrónico o, en otras expresiones de cálculo, se usa para enlazar un nombre a un resultado, que es del tipo de cálculo.|
|`match`|[Expresiones de coincidencia](match-expressions.md)|Se utiliza para bifurcar comparando un valor con un patrón.|
|`match!`|[Expresiones de cálculo](computation-expressions.md#match)|Se utiliza para inlinear una llamada a una expresión de cálculo y coincidencia de patrón en su resultado.|
|`member`|[Miembros](./members/index.md)|Se utiliza para declarar una propiedad o método en un tipo de objeto.|
|`module`|[Módulos](modules.md)|Se utiliza para asociar un nombre a un grupo de tipos, valores y funciones relacionados para separarlo lógicamente de otro código.|
|`mutable`|[Enlaces let](./functions/let-bindings.md)|Se utiliza para declarar una variable, es decir, un valor que se puede cambiar.|
|`namespace`|[Espacios de nombres](namespaces.md)|Se utiliza para asociar un nombre a un grupo de tipos y módulos relacionados, para separarlo lógicamente de otro código.|
|`new`|[Constructores](./members/constructors.md)<br /><br />[Restricciones](./generics/constraints.md)|Se utiliza para declarar, definir o invocar un constructor que crea o puede crear un objeto.<br /><br />También se utiliza en restricciones de parámetros genéricos para indicar que un tipo debe tener un constructor determinado.|
|`not`|[Referencia de símbolos y operadores](./symbol-and-operator-reference/index.md)<br /><br />[Restricciones](./generics/constraints.md)|En realidad no es una palabra clave. Sin `not struct` embargo, en combinación se utiliza como una restricción de parámetro genérico.|
|`null`|[Valores NULL](./values/null-values.md)<br /><br />[Restricciones](./generics/constraints.md)|Indica la ausencia de un objeto.<br /><br />También se utiliza en restricciones de parámetros genéricos.|
|`of`|[Uniones discriminadas](discriminated-unions.md)<br /><br />[Delegados](delegates.md)<br /><br />[Tipos de excepción](./exception-handling/exception-types.md)|Se utiliza en uniones discriminadas para indicar el tipo de categorías de valores y en las declaraciones de delegado y excepción.|
|`open`|[Declaraciones de importación: la palabra clave `open`](import-declarations-the-open-keyword.md)|Se utiliza para hacer que el contenido de un espacio de nombres o módulo esté disponible sin calificación.|
|`or`|[Referencia de símbolos y operadores](./symbol-and-operator-reference/index.md)<br /><br />[Restricciones](./generics/constraints.md)|Se utiliza con condiciones `or` booleanas como un operador booleano. Equivalente a `||`.<br /><br />También se utiliza en restricciones de miembro.|
|`override`|[Miembros](./members/index.md)|Se utiliza para implementar una versión de un método abstracto o virtual que difiere de la versión base.|
|`private`|[Control de acceso](access-control.md)|Restringe el acceso a un miembro al código del mismo tipo o módulo.|
|`public`|[Control de acceso](access-control.md)|Permite el acceso a un miembro desde fuera del tipo.|
|`rec`|[Funciones](./functions/index.md)|Se utiliza para indicar que una función es recursiva.|
|`return`|[Flujos de trabajo asincrónicos](Asynchronous-Workflows.md)<br /><br />[Expresiones de cálculo](computation-expressions.md)|Se utiliza para indicar un valor que se va a proporcionar como resultado de una expresión de cálculo.|
|`return!`|[Expresiones de cálculo](computation-expressions.md)<br /><br />[Flujos de trabajo asincrónicos](asynchronous-workflows.md)|Se utiliza para indicar una expresión de cálculo que, cuando se evalúa, proporciona el resultado de la expresión de cálculo contenedora.|
|`select`|[Expresiones de consulta](query-expressions.md)|Se utiliza en expresiones de consulta para especificar qué campos o columnas se van a extraer. Tenga en cuenta que se trata de una palabra clave contextual, lo que significa que en realidad no es una palabra reservada y solo actúa como una palabra clave en el contexto adecuado.|
|`static`|[Miembros](./members/index.md)|Se utiliza para indicar un método o propiedad que se puede llamar sin una instancia de un tipo o un miembro de valor que se comparte entre todas las instancias de un tipo.|
|`struct`|[Estructuras](structures.md)<br /><br /> [Tuplas](tuples.md)<br/><br/>[Restricciones](./generics/constraints.md)|Se utiliza para declarar un tipo de estructura.<br /><br/>Se utiliza para especificar una tupla struct.<br/><br />También se utiliza en restricciones de parámetros genéricos.<br /><br />Se utiliza para la compatibilidad con OCaml en las definiciones de módulo.|
|`then`|[Expresiones condicionales:`if...then...else`](conditional-expressions-if-then-else.md)<br /><br />[Constructores](./members/constructors.md)|Se utiliza en expresiones condicionales.<br /><br />También se utiliza para realizar efectos secundarios después de la construcción del objeto.|
|`to`|[Bucles: expresión `for...to`](loops-for-to-expression.md)|Se `for` utiliza en bucles para indicar un rango.|
|`true`|[Tipos primitivos](basic-types.md)|Se utiliza como literal booleano.|
|`try`|[Excepciones: expresión try...with](./exception-handling/the-try-with-expression.md)<br /><br />[Excepciones: expresión try...finally](./exception-handling/the-try-finally-expression.md)|Se utiliza para introducir un bloque de código que podría generar una excepción. Utilizado junto `with` `finally`con o .|
|`type`|[Tipos en F#](fsharp-types.md)<br /><br />[Clases](classes.md)<br /><br />[Registros](records.md)<br /><br />[Estructuras](structures.md)<br /><br />[Enumeraciones](enumerations.md)<br /><br />[Uniones discriminadas](discriminated-unions.md)<br /><br />[Abreviaturas de tipo](type-abbreviations.md)<br /><br />[Unidades de medida](units-of-measure.md)|Se utiliza para declarar una clase, registro, estructura, unión discriminada, tipo de enumeración, unidad de medida o abreviatura de tipo.|
|`upcast`|[Conversiones](casting-and-conversions.md)|Se utiliza para convertir a un tipo que es superior en la cadena de herencia.|
|`use`|[Administración de `use` recursos: La palabra clave](resource-management-the-use-keyword.md)|Se utiliza `let` en lugar `Dispose` de para los valores que requieren ser llamados para liberar recursos.|
|`use!`|[Expresiones de cálculo](computation-expressions.md)<br /><br />[Flujos de trabajo asincrónicos](asynchronous-workflows.md)|Se utiliza `let!` en lugar de en flujos `Dispose` de trabajo asincrónicos y otras expresiones de cálculo para los valores que requieren ser llamados para liberar recursos.|
|`val`|[Campos explícitos: la `val` palabra clave](./members/explicit-fields-the-val-keyword.md)<br /><br />[Firmas](signature-files.md)<br /><br />[Miembros](./members/index.md)|Se utiliza en una firma para indicar un valor, o en un tipo para declarar un miembro, en situaciones limitadas.|
|`void`|[Tipos primitivos](basic-types.md)|Indica el tipo `void` .NET. Se utiliza al interoperar con otros lenguajes .NET.|
|`when`|[Restricciones](./generics/constraints.md)|Se utiliza para condiciones booleanas *(cuando protege)* en coincidencias de patrones y para introducir una cláusula de restricción para un parámetro de tipo genérico.|
|`while`|[Bucles: expresión `while...do`](loops-while-do-expression.md)|Presenta una construcción de bucle.|
|`with`|[Expresiones de coincidencia](match-expressions.md)<br /><br />[Expresiones de objeto](object-expressions.md)<br /><br />[Expresiones de registro de copia y actualización](copy-and-update-record-expressions.md)<br /><br />[Extensiones de tipo](type-extensions.md)<br /><br />[Excepciones: `try...with` La expresión](./exception-handling/the-try-with-expression.md)|Se utiliza `match` junto con la palabra clave en expresiones de coincidencia de patrones. También se usa en expresiones de objeto, expresiones de copia de registros y extensiones de tipo para introducir definiciones de miembro e introducir controladores de excepciones.|
|`yield`|[Listas](lists.md), [Matrices](arrays.md), [Secuencias](sequences.md)|Se utiliza en una expresión de lista, matriz o secuencia para generar un valor para una secuencia. Normalmente se puede omitir, ya que está implícito en la mayoría de las situaciones.|
|`yield!`|[Expresiones de cálculo](computation-expressions.md)<br /><br />[Flujos de trabajo asincrónicos](asynchronous-workflows.md)|Se utiliza en una expresión de cálculo para anexar el resultado de una expresión de cálculo determinada a una colección de resultados para la expresión de cálculo contenedora.|

Los siguientes tokens se reservan en F- porque son palabras clave en el idioma OCaml:

- `asr`
- `land`
- `lor`
- `lsl`
- `lsr`
- `lxor`
- `mod`
- `sig`

Si utiliza `--mlcompatibility` la opción del compilador, las palabras clave anteriores están disponibles para su uso como identificadores.

Los siguientes tokens se reservan como palabras clave para la futura expansión del lenguaje F-

- `atomic`
- `break`
- `checked`
- `component`
- `const`
- `constraint`
- `constructor`
- `continue`
- `eager`
- `event`
- `external`
- `functor`
- `include`
- `method`
- `mixin`
- `object`
- `parallel`
- `process`
- `protected`
- `pure`
- `sealed`
- `tailcall`
- `trait`
- `virtual`
- `volatile`

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje f](index.md)
- [Referencia de símbolos y operadores](./symbol-and-operator-reference/index.md)
- [Opciones del compilador](compiler-options.md)
