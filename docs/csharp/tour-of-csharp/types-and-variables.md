---
title: 'Variables y tipos de C#: un paseo por el lenguaje C#'
description: Obtenga información sobre cómo definir tipos y declarar variables de C#
ms.date: 08/10/2016
ms.assetid: f8a8051e-0049-43f1-b594-9c84cc7b1224
ms.openlocfilehash: 34b724dff17feb699d797e9ed9aea25d85d8c5a9
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129524"
---
# <a name="types-and-variables"></a>Tipos y variables

Hay dos clases de tipos en C#: *tipos de valor* y *tipos de referencia*. Las variables de tipos de valor contienen directamente los datos, mientras que las variables de los tipos de referencia almacenan referencias a los datos, lo que se conoce como objetos. Con los tipos de referencia, es posible que dos variables hagan referencia al mismo objeto y que, por tanto, las operaciones en una variable afecten al objeto al que hace referencia la otra variable. Con los tipos de valor, cada variable tiene su propia copia de los datos y no es posible que las operaciones en una variable afecten a la otra (excepto en el caso de las variables de parámetro `ref` y `out`).

Los tipos de valor de C# se dividen en *tipos simples*, *tipos de enumeración*, *tipos de estructura* y *tipos de valores NULL*. Los tipos de referencia de C# se dividen en *tipos de clase*, *tipos de interfaz*, *tipos de matriz* y *tipos delegados*.

A continuación se proporciona información general del sistema de tipos de C#.

* Tipos de valor
    - Tipos simples
        * Entero con signo: `sbyte`, `short`, `int`,`long`
        * Entero sin signo: `byte`, `ushort`, `uint`,`ulong`
        * Caracteres Unicode: `char`
        * Punto flotante de IEEE: `float`, `double`
        * Decimal de alta precisión: `decimal`
        * Booleano: `bool`
    - Tipos de enumeración
        * Tipos definidos por el usuario con el formato `enum E {...}`
    - Tipos de estructura
        * Tipos definidos por el usuario con el formato `struct S {...}`
    - Tipos de valor que aceptan valores NULL
        * Extensiones de todos los demás tipos de valor con un valor `null`
* Tipos de referencia
    - Tipos de clase
        * Clase base definitiva de todos los demás tipos: `object`
        * Cadenas Unicode: `string`
        * Tipos definidos por el usuario con el formato `class C {...}`
    - Tipos de interfaz
        * Tipos definidos por el usuario con el formato `interface I {...}`
    - Tipos de matriz
        * Unidimensional y multidimensional; por ejemplo, `int[]` y `int[,]`
    - Tipos delegados
        * Tipos definidos por el usuario con el formato `delegate int D(...)`

Los ocho tipos enteros proporcionan compatibilidad con valores de 8, 16, 32 y 64 bits en formato con o sin signo.

Los dos tipos de punto flotante, `float` y `double`, se representan mediante los formatos IEC-60559 de precisión sencilla de 32 bits y de doble precisión de 64 bits, respectivamente.

El tipo `decimal` es un tipo de datos de 128 bits adecuado para cálculos financieros y monetarios.

El tipo `bool` de C# se utiliza para representar valores booleanos; valores que son `true` o `false`.

El procesamiento de caracteres y cadenas en C# utiliza la codificación Unicode. El tipo `char` representa una unidad de código UTF-16 y el tipo `string` representa una secuencia de unidades de código UTF-16.

Resume los tipos numéricos de C#.

* Entero con signo
    - `sbyte`: 8 bits, de -128 a 127
    - `short`: 16 bits, de -32,768 a 32,767
    - `int`: 32 bits, de -2,147,483,648 a 2,147,483,647
    - `long`: 64 bits, de -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807
* Entero sin signo
    - `byte`: 8 bits, de 0 a 255
    - `ushort`: 16 bits, de 0 a 65,535
    - `uint`: 32 bits, de 0 a 4,294,967,295
    - `ulong`: 64 bits, de 0 a 18,446,744,073,709,551,615
* Punto flotante
    - `float`: 32 bits, de 1.5 × 10<sup>−45</sup> a 3.4 × 10<sup>38</sup>, precisión de 7 dígitos
    - `double`: 64 bits, de 5.0 × 10<sup>−324</sup> a 1.7 × 10<sup>308</sup>, precisión de 15 dígitos
* Decimal
    - `decimal`: 128 bits, al menos de –7.9 × 10<sup>−28</sup> a 7.9 × 10<sup>28</sup>, con una precisión mínima de 28 dígitos
    
Los programas de C# utilizan *declaraciones de tipos* para crear nuevos tipos. Una declaración de tipos especifica el nombre y los miembros del nuevo tipo. Cinco de las categorías de tipos de C# las define el usuario: tipos de clase, tipos de estructura, tipos de interfaz, tipos de enumeración y tipos delegados.

A tipo `class` define una estructura de datos que contiene miembros de datos (campos) y miembros de función (métodos, propiedades y otros). Los tipos de clase admiten herencia única y polimorfismo, mecanismos por los que las clases derivadas pueden extender y especializar clases base.

Un tipo `struct` es similar a un tipo de clase, por el hecho de que representa una estructura con miembros de datos y miembros de función. Sin embargo, a diferencia de las clases, las estructuras son tipos de valor y no suelen requerir la asignación del montón. Los tipos struct no admiten la herencia especificada por el usuario y todos los tipos de struct se heredan implícitamente del tipo `object`.

Un tipo `interface` define un contrato como un conjunto con nombre de miembros de función públicos. Un `class` o `struct` que implementa un `interface` debe proporcionar implementaciones de miembros de función de la interfaz. Un `interface` puede heredar de varias interfaces base, y un `class` o `struct` pueden implementar varias interfaces.

Un tipo `delegate` representa las referencias a métodos con una lista de parámetros determinada y un tipo de valor devuelto. Los delegados permiten tratar métodos como entidades que se puedan asignar a variables y se puedan pasar como parámetros. Los delegados son análogos a los tipos de función proporcionados por los lenguajes funcionales. Son similares al concepto de punteros de función en otros lenguajes, pero a diferencia de los punteros de función, los delegados están orientados a objetos y presentan seguridad de tipos.

Los tipos `class`, `struct`, `interface` y `delegate` admiten parámetros genéricos, mediante los cuales se pueden parametrizar con otros tipos.

Un tipo `enum` es un tipo distinto con constantes con nombre. Cada tipo `enum` tiene un tipo subyacente, que debe ser uno de los ocho tipos enteros. El conjunto de valores de un tipo `enum` es igual que el conjunto de valores del tipo subyacente.

C# admite matrices unidimensionales y multidimensionales de cualquier tipo. A diferencia de los tipos enumerados anteriormente, los tipos de matriz no tienen que ser declarados antes de usarlos. En su lugar, los tipos de matriz se crean mediante un nombre de tipo entre corchetes. Por ejemplo, `int[]` es una matriz unidimensional de `int`, `int[,]` es una matriz bidimensional de `int` y `int[][]` es una matriz unidimensional de la matriz unidimensional de `int`.

Los tipos de valor NULL tampoco tienen que ser declarados antes de usarlos. Para cada tipo de valor distinto de NULL `T`, existe un tipo de valor NULL correspondiente `T?`, que puede tener un valor adicional, `null`. Por ejemplo, `int?` es un tipo que puede contener cualquier número entero de 32 bits o el valor `null`.

El sistema de tipos de C# está unificado, de tal forma que un valor de cualquier tipo puede tratarse como un `object`. Todos los tipos de C# directa o indirectamente se derivan del tipo de clase `object`, y `object` es la clase base definitiva de todos los tipos. Los valores de tipos de referencia se tratan como objetos mediante la visualización de los valores como tipo `object`. Los valores de tipos de valor se tratan como objetos mediante la realización de *operaciones de conversión boxing* y *operaciones de conversión unboxing*. En el ejemplo siguiente, un valor `int` se convierte en `object` y vuelve a `int`.

[!code-csharp[Boxing](../../../samples/snippets/csharp/tour/types-and-variables/Program.cs#L1-L10)]

Cuando se convierte un valor de un tipo de valor al tipo `object`, se asigna una instancia `object`, también denominada "box", para contener el valor, y el valor se copia en dicho box. Por el contrario, cuando se convierte una referencia `object` en un tipo de valor, se comprueba si la referencia `object` es un box del tipo de valor correcto y, si la comprobación es correcta, se copia el valor del box.

El sistema de tipos unificado de C# conlleva efectivamente que los tipos de valor pueden convertirse en objetos "a petición". Debido a la unificación, las bibliotecas de uso general que utilizan el tipo `object` pueden usarse con tipos de referencia y tipos de valor.

Hay varios tipos de *variables* en C#, entre otras, campos, elementos de matriz, variables locales y parámetros. Las variables representan ubicaciones de almacenamiento, y cada variable tiene un tipo que determina qué valores pueden almacenarse en la variable, como se muestra a continuación.

* Tipo de valor distinto a NULL
    - Un valor de ese tipo exacto
* Tipos de valor NULL
    - Un valor `null` o un valor de ese tipo exacto
* objeto
    - Una referencia `null`, una referencia a un objeto de cualquier tipo de referencia o una referencia a un valor de conversión boxing de cualquier tipo de valor
* Tipo de clase
    - Una referencia `null`, una referencia a una instancia de ese tipo de clase o una referencia a una instancia de una clase derivada de ese tipo de clase
* Tipo de interfaz
    - Un referencia `null`, una referencia a una instancia de un tipo de clase que implementa dicho tipo de interfaz o una referencia a un valor de conversión boxing de un tipo de valor que implementa dicho tipo de interfaz
* Tipo de matriz
    - Una referencia `null`, una referencia a una instancia de ese tipo de matriz o una referencia a una instancia de un tipo de matriz compatible
* Tipo delegado
    - Una referencia `null` o una referencia a una instancia de un tipo delegado compatible

>[!div class="step-by-step"]
>[Anterior](program-structure.md)
>[Siguiente](expressions.md)