---
title: Referencia de palabras clave
description: 'Busque vínculos a información sobre todas las palabras clave del lenguaje F #.'
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
- const_FS
dev_langs:
- FSharp
ms.date: 08/15/2020
ms.openlocfilehash: 15505c123dd0d6497fbc80c8fc9f0910018911ea
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558106"
---
# <a name="keyword-reference"></a>Referencia de palabras clave

Este tema contiene vínculos a información sobre todas las palabras clave del lenguaje F #.

## <a name="f-keyword-table"></a>Tabla de palabras clave de F #

En la tabla siguiente se muestran todas las palabras clave de F # en orden alfabético, junto con breves descripciones y vínculos a temas relevantes que contienen más información.

|Palabra clave|Vínculo|Descripción|
|-------|----|-----------|
|`abstract`|[Miembros](./members/index.md)<br /><br />[Clases abstractas](abstract-classes.md)|Indica un método que no tiene ninguna implementación en el tipo en el que se declara o que es virtual y tiene una implementación predeterminada.|
|`and`|[`let` Enlaces](./functions/let-bindings.md)<br /><br />[Registros](records.md)<br /><br />[Miembros](./members/index.md)<br /><br />[Restricciones](./generics/constraints.md)|Se utiliza en enlaces y registros recursivos mutuamente, en las declaraciones de propiedad y con varias restricciones en los parámetros genéricos.|
|`as`|[Clases](classes.md)<br /><br />[Coincidencia de patrones](Pattern-Matching.md)|Se utiliza para asignar un nombre de objeto al objeto de clase actual. También se usa para asignar un nombre a un patrón entero dentro de una coincidencia de patrones.|
|`assert`|[Aserciones](assertions.md)|Se utiliza para comprobar el código durante la depuración.|
|`base`|[Clases](classes.md)<br /><br />[Herencia](inheritance.md)|Se utiliza como el nombre del objeto de la clase base.|
|`begin`|[Sintaxis detallada](verbose-syntax.md)|En la sintaxis detallada, indica el inicio de un bloque de código.|
|`class`|[Clases](classes.md)|En la sintaxis detallada, indica el inicio de una definición de clase.|
|`default`|[Miembros](./members/index.md)|Indica una implementación de un método abstracto; se utiliza junto con una declaración de método abstracto para crear un método virtual.|
|`delegate`|[Delegados](delegates.md)|Se usa para declarar un delegado.|
|`do`|[do (Enlaces)](./functions/do-bindings.md)<br /><br />[Bucles: expresión `for...to`](loops-for-to-expression.md)<br /><br />[Bucles: expresión `for...in`](loops-for-in-expression.md)<br /><br />[Bucles: expresión `while...do`](loops-while-do-expression.md)|Se utiliza en construcciones de bucle o para ejecutar código imperativo.|
|`done`|[Sintaxis detallada](verbose-syntax.md)|En la sintaxis detallada, indica el final de un bloque de código en una expresión de bucle.|
|`downcast`|[Conversiones](casting-and-conversions.md)|Se usa para convertir a un tipo que está más abajo en la cadena de herencia.|
|`downto`|[Bucles: expresión `for...to`](loops-for-to-expression.md)|En una `for` expresión, se utiliza al contar en orden inverso.|
|`elif`|[Expresiones condicionales: `if...then...else`](conditional-expressions-if-then-else.md)|Se usa en la bifurcación condicional. Forma abreviada de `else if` .|
|`else`|[Expresiones condicionales: `if...then...else`](conditional-expressions-if-then-else.md)|Se usa en la bifurcación condicional.|
|`end`|[Estructuras](structures.md)<br /><br />[Uniones discriminadas](discriminated-unions.md)<br /><br />[Registros](records.md)<br /><br />[Extensiones de tipo](type-extensions.md)<br /><br />[Sintaxis detallada](verbose-syntax.md)|En definiciones de tipo y extensiones de tipo, indica el final de una sección de definiciones de miembros.<br /><br />En la sintaxis detallada, se usa para especificar el final de un bloque de código que comienza con la `begin` palabra clave.|
|`exception`|[Control de excepciones](./exception-handling/index.md)<br /><br />[Tipos de excepción](./exception-handling/exception-types.md)|Se utiliza para declarar un tipo de excepción.|
|`extern`|[Funciones externas](./functions/external-functions.md)|Indica que un elemento de programa declarado está definido en otro binario o ensamblado.|
|`false`|[Tipos primitivos](basic-types.md)|Se usa como un literal booleano.|
|`finally`|[Excepciones: la `try...finally` expresión](./exception-handling/the-try-finally-expression.md)|Se usa junto con `try` para introducir un bloque de código que se ejecuta independientemente de si se produce una excepción.|
|`fixed`|[Resuelto](fixed.md)|Se usa para "anclar" un puntero en la pila para impedir que se recopile el elemento no utilizado.|
|`for`|[Bucles: expresión `for...to`](loops-for-to-expression.md)<br /><br />[Bucles: expresión for...in](loops-for-in-expression.md)|Se utiliza en construcciones de bucle.|
|`fun`|[Expresiones lambda: `fun` palabra clave](./functions/lambda-expressions-the-fun-keyword.md)|Se usa en expresiones lambda, también conocidas como funciones anónimas.|
|`function`|[Expresiones de coincidencia](match-expressions.md)<br /><br />[Expresiones lambda: palabra clave Fun](./functions/lambda-expressions-the-fun-keyword.md)|Se usa como una alternativa más corta a la `fun` palabra clave y una `match` expresión en una expresión lambda que tiene coincidencia de patrones en un solo argumento.|
|`global`|[Espacios de nombres](namespaces.md)|Se usa para hacer referencia al espacio de nombres .NET de nivel superior.|
|`if`|[Expresiones condicionales: `if...then...else`](conditional-expressions-if-then-else.md)|Se usa en construcciones de bifurcación condicional.|
|`in`|[Bucles: expresión for...in](loops-for-in-expression.md)<br /><br />[Sintaxis detallada](verbose-syntax.md)|Se usa para las expresiones de secuencia y, en la sintaxis detallada, para separar las expresiones de los enlaces.|
|`inherit`|[Herencia](inheritance.md)|Se utiliza para especificar una clase base o una interfaz base.|
|`inline`|[Funciones](./functions/index.md)<br /><br />[Funciones insertadas](./functions/inline-functions.md)|Se usa para indicar una función que debe integrarse directamente en el código del llamador.|
|`interface`|[Interfaces](interfaces.md)|Se usa para declarar e implementar interfaces.|
|`internal`|[Control de acceso](access-control.md)|Se usa para especificar que un miembro es visible dentro de un ensamblado, pero no fuera de él.|
|`lazy`|[Expresiones diferidas](lazy-expressions.md)|Se utiliza para especificar una expresión que se va a realizar solo cuando se necesita un resultado.|
|`let`|[`let` Enlaces](./functions/let-bindings.md)|Se utiliza para asociar o enlazar un nombre a un valor o una función.|
|`let!`|[Flujos de trabajo asincrónicos](asynchronous-workflows.md)<br /><br />[Expresiones de cálculo](computation-expressions.md)|Se usa en flujos de trabajo asincrónicos para enlazar un nombre al resultado de un cálculo asincrónico, o bien, en otras expresiones de cálculo, que se usa para enlazar un nombre a un resultado, que es del tipo de cálculo.|
|`match`|[Expresiones de coincidencia](match-expressions.md)|Se usa para bifurcar mediante la comparación de un valor con un patrón.|
|`match!`|[Expresiones de cálculo](computation-expressions.md#match)|Se usa para alinear una llamada a una expresión de cálculo y una coincidencia de patrón en su resultado.|
|`member`|[Miembros](./members/index.md)|Se utiliza para declarar una propiedad o un método en un tipo de objeto.|
|`module`|[Módulos](modules.md)|Se utiliza para asociar un nombre a un grupo de tipos, valores y funciones relacionados, para separarlo lógicamente de otro código.|
|`mutable`|[Enlaces let](./functions/let-bindings.md)|Se utiliza para declarar una variable, es decir, un valor que se puede cambiar.|
|`namespace`|[Espacios de nombres](namespaces.md)|Se usa para asociar un nombre a un grupo de tipos y módulos relacionados, para separarlo lógicamente de otro código.|
|`new`|[Constructores](./members/constructors.md)<br /><br />[Restricciones](./generics/constraints.md)|Se utiliza para declarar, definir o invocar un constructor que crea o que puede crear un objeto.<br /><br />También se utiliza en las restricciones de parámetros genéricos para indicar que un tipo debe tener un determinado constructor.|
|`not`|[Referencia de símbolos y operadores](./symbol-and-operator-reference/index.md)<br /><br />[Restricciones](./generics/constraints.md)|En realidad, no es una palabra clave. Sin embargo, `not struct` en combinación se utiliza como una restricción de parámetro genérico.|
|`null`|[Valores NULL](./values/null-values.md)<br /><br />[Restricciones](./generics/constraints.md)|Indica la ausencia de un objeto.<br /><br />También se utiliza en las restricciones de parámetros genéricos.|
|`of`|[Uniones discriminadas](discriminated-unions.md)<br /><br />[Delegados](delegates.md)<br /><br />[Tipos de excepción](./exception-handling/exception-types.md)|Se usa en uniones discriminadas para indicar el tipo de categorías de valores y en declaraciones de delegado y de excepción.|
|`open`|[Declaraciones de importación: la palabra clave `open`](import-declarations-the-open-keyword.md)|Se usa para hacer que el contenido de un espacio de nombres o módulo esté disponible sin calificación.|
|`or`|[Referencia de símbolos y operadores](./symbol-and-operator-reference/index.md)<br /><br />[Restricciones](./generics/constraints.md)|Se usa con condiciones booleanas como `or` operador booleano. Equivalente a `||`.<br /><br />También se usa en restricciones de miembro.|
|`override`|[Miembros](./members/index.md)|Se utiliza para implementar una versión de un método abstracto o virtual que difiere de la versión base.|
|`private`|[Control de acceso](access-control.md)|Restringe el acceso a un miembro al código en el mismo tipo o módulo.|
|`public`|[Control de acceso](access-control.md)|Permite el acceso a un miembro desde fuera del tipo.|
|`rec`|[Funciones](./functions/index.md)|Se utiliza para indicar que una función es recursiva.|
|`return`|[Flujos de trabajo asincrónicos](Asynchronous-Workflows.md)<br /><br />[Expresiones de cálculo](computation-expressions.md)|Se utiliza para indicar un valor que se va a proporcionar como resultado de una expresión de cálculo.|
|`return!`|[Expresiones de cálculo](computation-expressions.md)<br /><br />[Flujos de trabajo asincrónicos](asynchronous-workflows.md)|Se utiliza para indicar una expresión de cálculo que, cuando se evalúa, proporciona el resultado de la expresión de cálculo que lo contiene.|
|`select`|[Expresiones de consulta](query-expressions.md)|Se usa en expresiones de consulta para especificar qué campos o columnas se van a extraer. Tenga en cuenta que se trata de una palabra clave contextual, lo que significa que no es realmente una palabra reservada y que solo actúa como una palabra clave en el contexto adecuado.|
|`static`|[Miembros](./members/index.md)|Se utiliza para indicar un método o una propiedad que se puede llamar sin una instancia de un tipo, o un miembro de valor que se comparte entre todas las instancias de un tipo.|
|`struct`|[Estructuras](structures.md)<br /><br /> [Tuplas](tuples.md)<br/><br/>[Restricciones](./generics/constraints.md)|Se utiliza para declarar un tipo de estructura.<br /><br/>Se usa para especificar una tupla de struct.<br/><br />También se utiliza en las restricciones de parámetros genéricos.<br /><br />Se usa para la compatibilidad de OCaml en las definiciones de módulo.|
|`then`|[Expresiones condicionales: `if...then...else`](conditional-expressions-if-then-else.md)<br /><br />[Constructores](./members/constructors.md)|Se usa en expresiones condicionales.<br /><br />También se usa para realizar efectos secundarios después de la construcción del objeto.|
|`to`|[Bucles: expresión `for...to`](loops-for-to-expression.md)|Se utiliza en `for` bucles para indicar un intervalo.|
|`true`|[Tipos primitivos](basic-types.md)|Se usa como un literal booleano.|
|`try`|[Excepciones: expresión try...with](./exception-handling/the-try-with-expression.md)<br /><br />[Excepciones: expresión try...finally](./exception-handling/the-try-finally-expression.md)|Se usa para introducir un bloque de código que podría generar una excepción. Se usa junto con `with` o `finally` .|
|`type`|[Tipos en F#](fsharp-types.md)<br /><br />[Clases](classes.md)<br /><br />[Registros](records.md)<br /><br />[Estructuras](structures.md)<br /><br />[Enumeraciones](enumerations.md)<br /><br />[Uniones discriminadas](discriminated-unions.md)<br /><br />[Abreviaturas de tipo](type-abbreviations.md)<br /><br />[Unidades de medida](units-of-measure.md)|Se usa para declarar una clase, un registro, una estructura, una Unión discriminada, un tipo de enumeración, una unidad de medida o una abreviatura de tipo.|
|`upcast`|[Conversiones](casting-and-conversions.md)|Se utiliza para convertir a un tipo que es mayor en la cadena de herencia.|
|`use`|[Administración de recursos: `use`Palabra clave](resource-management-the-use-keyword.md)|Se usa en lugar de `let` para los valores que requieren que `Dispose` se llame a para liberar recursos.|
|`use!`|[Expresiones de cálculo](computation-expressions.md)<br /><br />[Flujos de trabajo asincrónicos](asynchronous-workflows.md)|Se usa en lugar de `let!` en flujos de trabajo asincrónicos y otras expresiones de cálculo para los valores que requieren que `Dispose` se llame a para liberar recursos.|
|`val`|[Campos explícitos: `val` palabra clave](./members/explicit-fields-the-val-keyword.md)<br /><br />[Firmas](signature-files.md)<br /><br />[Miembros](./members/index.md)|Se usa en una firma para indicar un valor, o en un tipo para declarar un miembro, en situaciones limitadas.|
|`void`|[Tipos primitivos](basic-types.md)|Indica el `void` tipo .net. Se usa al interoperar con otros lenguajes .NET.|
|`when`|[Restricciones](./generics/constraints.md)|Se usa para las condiciones booleanas (*cuando las protege*) en las coincidencias de patrones y para introducir una cláusula de restricción para un parámetro de tipo genérico.|
|`while`|[Bucles: expresión `while...do`](loops-while-do-expression.md)|Introduce una construcción de bucle.|
|`with`|[Expresiones de coincidencia](match-expressions.md)<br /><br />[Expresiones de objeto](object-expressions.md)<br /><br />[Expresiones de registro de copia y actualización](copy-and-update-record-expressions.md)<br /><br />[Extensiones de tipo](type-extensions.md)<br /><br />[Excepciones: la `try...with` expresión](./exception-handling/the-try-with-expression.md)|Se usa junto con la `match` palabra clave en expresiones de coincidencia de patrones. También se usa en expresiones de objeto, expresiones de copia de registros y extensiones de tipo para introducir definiciones de miembros, y para introducir controladores de excepciones.|
|`yield`|[Listas](lists.md), [matrices](arrays.md), [secuencias](sequences.md)|Se utiliza en una lista, matriz o expresión de secuencia para generar un valor para una secuencia. Normalmente se puede omitir, ya que es implícita en la mayoría de los casos.|
|`yield!`|[Expresiones de cálculo](computation-expressions.md)<br /><br />[Flujos de trabajo asincrónicos](asynchronous-workflows.md)|Se utiliza en una expresión de cálculo para anexar el resultado de una expresión de cálculo determinada a una colección de resultados para la expresión de cálculo que lo contiene.|
|`const`|[Proveedores de tipos](../tutorials/type-providers/index.md)| Los proveedores de tipos permiten el uso de `const` como una palabra clave para especificar un literal constante como argumento de tipo de parámetro.|

Los tokens siguientes están reservados en F # porque son palabras clave en el lenguaje OCaml:

- `asr`
- `land`
- `lor`
- `lsl`
- `lsr`
- `lxor`
- `mod`
- `sig`

Si usa la `--mlcompatibility` opción del compilador, las palabras clave anteriores se pueden usar como identificadores.

Los tokens siguientes están reservados como palabras clave para una futura ampliación del lenguaje F #:

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

- [Referencia del lenguaje F#](index.md)
- [Referencia de símbolos y operadores](./symbol-and-operator-reference/index.md)
- [Opciones del compilador](compiler-options.md)
