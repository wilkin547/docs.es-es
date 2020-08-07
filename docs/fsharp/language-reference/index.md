---
title: Referencia del lenguaje
description: Aquí encontrará información de características del lenguaje F# como tokens del lenguaje, conceptos, tipos, expresiones y temas de constructos compatibles con el compilador.
ms.date: 05/16/2016
ms.openlocfilehash: e8a6c7ef83c4e2d292cc6a12a59e420708240a39
ms.sourcegitcommit: 09bad6ec0cbf18be7cd7f62e77286d305a18b607
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2020
ms.locfileid: "87795481"
---
# <a name="f-language-reference"></a>Referencia del lenguaje F#

Esta sección es una referencia al lenguaje F#, un lenguaje de programación multiparadigmático con .NET como destino. El lenguaje F# admite los modelos de programación funcional, orientada a objetos e imperativa.

## <a name="f-tokens"></a>Tokens de F#

En la tabla siguiente se muestran temas de referencia que proporcionan tablas de palabras clave, símbolos y literales que se usan como tokens en F#.

|Título|Descripción|
|-----|-----------|
|[Referencia de palabras clave](keyword-reference.md)|Contiene vínculos a información sobre todas las palabras clave del lenguaje F#.|
|[Referencia de símbolos y operadores](./symbol-and-operator-reference/index.md)|Contiene una tabla de símbolos y operadores que se usan en el lenguaje F#.|
|[Literales](literals.md)|Describe la sintaxis de los valores literales en F# y cómo especificar la información de tipos para los literales de F#.|

## <a name="f-language-concepts"></a>Conceptos del lenguaje F#

En la tabla siguiente se muestran los temas de referencia disponibles que describen los conceptos del lenguaje.

|Título|Descripción|
|-----|-----------|
|[Funciones](./functions/index.md)|Las funciones son la unidad fundamental de la ejecución del programa en cualquier lenguaje de programación. Al igual que en otros lenguajes, una función de F# tiene un nombre, puede tener parámetros y tomar argumentos, y tiene un cuerpo. F# también admite construcciones de programación funcional como el tratamiento de las funciones como valores, el uso de funciones sin nombre en expresiones, la composición de funciones para crear nuevas funciones, funciones currificadas y la definición implícita de funciones mediante la aplicación parcial de argumentos de función.|
|[Tipos en F#](fsharp-types.md)|Describe los tipos que se usan en F#, cómo se les asigna un nombre y se describen.|
|[Inferencia de tipos](type-inference.md)|Describe cómo el compilador de F# realiza la inferencia de los tipos de valor, variables, parámetros y valores devueltos.|
|[Generalización automática](./generics/automatic-generalization.md)|Describe las construcciones genéricas en F#.|
|[Herencia](inheritance.md)|Describe la herencia, que se usa para modelar la relación de identidad o los subtipos en la programación orientada a objetos.|
|[Miembros](./members/index.md)|Describe los miembros de los tipos de objeto de F#.|
|[Parámetros y argumentos](Parameters-and-Arguments.md)|Describe la compatibilidad con lenguajes para definir parámetros y pasar argumentos a las funciones, los métodos y las propiedades. Incluye información sobre cómo pasar por referencia.|
|[Sobrecarga de operadores](operator-overloading.md)|Describe cómo sobrecargar los operadores aritméticos de un tipo de clase o registro, así como en el nivel global.|
|[Conversiones](casting-and-conversions.md)|Describe la compatibilidad con las conversiones de tipos en F#.|
|[Control de acceso](access-control.md)|Describe el control de acceso en F#. El control de acceso se refiere a declarar qué clientes podrán usar determinados elementos de programa, tales como tipos, métodos, funciones, etc.|
|[Coincidencia de patrones](pattern-matching.md)|Describe los patrones, que son las reglas para transformar los datos de entrada que se usan en todo el lenguaje F# para extraer datos de comparación con un patrón, descomponer datos en sus partes constituyentes o extraer información de los datos de varias maneras.|
|[Patrones activos](active-patterns.md)|Describe los patrones activos. Los patrones activos permiten definir particiones con nombre que subdividen los datos de entrada. Se pueden usar patrones activos para descomponer los datos de manera personalizada para cada partición.|
|[Aserciones](assertions.md)|Describe la expresión `assert`, que es una característica de depuración que se puede usar para probar una expresión. En caso de error en modo de depuración, una aserción genera un cuadro de diálogo de error del sistema.|
|[Control de excepciones](./exception-handling/index.md)|Contiene información sobre la compatibilidad con el control de excepciones del lenguaje F#.|
|[attributes](attributes.md)|Describe los atributos, que permiten aplicar metadatos a una construcción de programación.|
|[Administración de recursos: `use`Palabra clave](resource-management-the-use-keyword.md)|Describe las palabras clave `use` y `using`, que permiten controlar la inicialización y la liberación de los recursos.|
|[namespaces](namespaces.md)|Describe la compatibilidad con los espacios de nombres en F#. Un espacio de nombres permite organizar el código en áreas de funcionalidad relacionada, lo que permite adjuntar un nombre a una agrupación de elementos de programa.|
|[Módulos](modules.md)|Describe los módulos. Un módulo de F# es una agrupación de código de F#, como valores, tipos y valores de función, en un programa de F#. Agrupar el código en módulos ayuda a mantener junto el código relacionado y a evitar conflictos de nombres en los programas.|
|[Declaraciones de importación: la palabra clave `open`](import-declarations-the-open-keyword.md)|Describe cómo funciona `open`. Una declaración de importación especifica un módulo o un espacio de nombres a cuyos elementos se puede hacer referencia sin usar un nombre completo.|
|[Firmas](signature-files.md)|Describe las firmas y los archivos de firma. Un archivo de signatura contiene información sobre las signaturas públicas de un conjunto de elementos de programa F# como, por ejemplo, tipos, espacios de nombres y módulos. Puede usarse para especificar la accesibilidad de estos elementos de programa.|
|[Documentación de XML](xml-documentation.md)|Describe la compatibilidad con la generación de archivos de documentación para comentarios de documentación XML, también denominados comentarios de barra diagonal triple. Se puede generar documentación a partir de los comentarios de código en F# exactamente igual que en los demás lenguajes .NET.|
|[Sintaxis detallada](verbose-syntax.md)|Describe la sintaxis para las construcciones de F# cuando no está habilitada la sintaxis ligera. La directiva `#light "off"` en la parte superior del archivo de código indica que se trata de la sintaxis detallada.|
|[Texto sin formato](plaintext-formatting.md)|Obtenga información sobre cómo usar sprintf y otros textos sin formato en scripts y aplicaciones de F#.|

## <a name="f-types"></a>Tipos en F#

En la tabla siguiente se muestran los temas de referencia disponibles que describen los tipos admitidos por el lenguaje F#.

|Título|Descripción|
|-----|-----------|
|[Valores](./values/index.md)|Describe los valores, que son cantidades inmutables que tienen un tipo específico. Los valores pueden ser números enteros o de punto flotante, caracteres o texto, listas, secuencias, matrices, tuplas, uniones discriminadas, registros, tipos de clase o valores de función.|
|[Tipos básicos](basic-types.md)|Describe los tipos básicos fundamentales que se usan en el lenguaje F#. También se proporcionan los tipos de .NET correspondientes y los valores máximos y mínimos para cada tipo.|
|[Unit (Tipo)](unit-type.md)|Describe el tipo `unit`, que indica la ausencia de un valor concreto. El tipo `unit` tiene solo un valor, que actúa como marcador de posición cuando no existe o no se necesita ningún otro valor.|
|[Cadenas](strings.md)|Describe las cadenas en F#. El tipo `string` representa texto inmutable como una secuencia de caracteres Unicode. `string` es un alias de `System.String` en .NET Framework.|
|[Tuplas](tuples.md)|Describe las tuplas, que son agrupaciones de valores sin nombre pero ordenados cuyos tipos pueden ser diferentes.|
|[Tipos de colección F#](fsharp-collection-types.md)|Información general de los tipos de colección funcionales de F#, incluidos los tipos de matrices, listas, secuencias (seq), asignaciones y conjuntos.|
|[Listas](lists.md)|Describe las listas. En F#, una lista es una serie ordenada e inmutable de elementos del mismo tipo.|
|[Opciones](options.md)|Describe el tipo de opción. En F#, se usa una opción cuando un valor puede o no existir. Una opción tiene un tipo subyacente y puede contener un valor de ese tipo o no tener ningún valor.|
|[Secuencias](sequences.md)|Describe las secuencias. Una secuencia es una serie lógica de elementos del mismo tipo. Los elementos individuales de la secuencia únicamente se calculan si es necesario, de modo que la representación pueda ser menor que lo que indica el recuento literal de elementos.|
|[Matrices](arrays.md)|Describe las matrices. Las matrices son secuencias mutables de tamaño fijo y basadas en cero de elementos de datos consecutivos, todos del mismo tipo.|
|[Registros](records.md)|Describe los registros. Los registros representan agregados simples de valores con nombre, opcionalmente con miembros.|
|[Uniones discriminadas](discriminated-unions.md)|Describe las uniones discriminadas, que proporcionan compatibilidad con valores que pueden ser uno de los diversos casos con nombre, cada uno con valores y tipos posiblemente diferentes.|
|[Enumeraciones](enumerations.md)|Describe las enumeraciones, que son tipos que tienen un conjunto definido de valores con nombre. Se pueden usar en lugar de los literales para que el código sea más fácil de leer y mantener.|
|[Celdas de referencia](reference-cells.md)|Describe las celdas de referencia, que son ubicaciones de almacenamiento que permiten crear variables mutables con semántica de referencias.|
|[Abreviaturas de tipo](type-abbreviations.md)|Describe las abreviaturas de tipo, que son nombres alternativos para los tipos.|
|[Clases](classes.md)|Describe las clases, que son tipos que representan objetos que pueden tener propiedades, métodos y eventos.|
|[Estructuras](structures.md)|Describe las estructuras, que son tipos de objeto compactos que pueden ser más eficaces que una clase para los tipos que tienen una pequeña cantidad de datos y un comportamiento simple.|
|[Interfaces](interfaces.md)|Describe las interfaces, que especifican conjuntos de miembros relacionados que otras clases implementan.|
|[Clases abstractas](abstract-classes.md)|Describe las clases abstractas, que son clases que dejan algunos o todos los miembros sin implementar para que las clases derivadas puedan proporcionar las implementaciones.|
|[Extensiones de tipo](type-extensions.md)|Describe las extensiones de tipo, que permiten agregar nuevos miembros a un tipo de objeto definido previamente.|
|[Tipos flexibles](flexible-types.md)|Describe los tipos flexibles. Una anotación de tipo flexible es una indicación de que un parámetro, una variable o un valor tiene un tipo que es compatible con el tipo especificado, de tal forma que la compatibilidad viene determinada por la posición en una jerarquía orientada a objetos de clases o interfaces.|
|[Delegados](delegates.md)|Describe los delegados, que representan una llamada de función como un objeto.|
|[Unidades de medida](units-of-measure.md)|Describe las unidades de medida. En F#, los valores de punto flotante pueden tener unidades de medida asociadas, que se suelen usar para indicar la longitud, el volumen, la masa, etc.|
|[Proveedores de tipos](../tutorials/type-providers/index.md)|Describe los proveedores de tipos y proporciona vínculos a tutoriales sobre el uso de los proveedores de tipos integrados para tener acceso a bases de datos y servicios web.|

## <a name="f-expressions"></a>Expresiones de F#

En la tabla siguiente se muestran los temas que describen las expresiones de F#.

|Título|Descripción|
|-----|-----------|
|[Expresiones condicionales: `if...then...else`](conditional-expressions-if-then-else.md)|Describe la expresión `if...then...else`, que ejecuta diferentes ramas de código y también se evalúa como un valor distinto según la expresión booleana especificada.|
|[Expresiones de coincidencia](match-expressions.md)|Describe la expresión `match`, que proporciona control de rama basado en la comparación de una expresión con un conjunto de patrones.|
|[Bucles: expresión `for...to`](loops-for-to-expression.md)|Describe la expresión `for...to`, que se usa para recorrer en iteración un bucle sobre un intervalo de valores de una variable de bucle.|
|[Bucles: expresión `for...in`](loops-for-in-expression.md)|Describe la expresión `for...in`, una construcción de bucle que se usa para recorrer en iteración las coincidencias de un patrón en una colección enumerable como una expresión de intervalo, una secuencia, una lista, una matriz u otra construcción que admita la enumeración.|
|[Bucles: expresión `while...do`](loops-while-do-expression.md)|Describe la expresión `while...do`, que se usa para realizar la ejecución iterativa (en bucle) mientras se cumple una condición de prueba especificada.|
|[Expresiones de objeto](object-expressions.md)|Describe las expresiones de objeto, que son las que crean nuevas instancias de un tipo de objeto anónimo creado dinámicamente que se basa en un tipo base, una interfaz o un conjunto de interfaces existente.|
|[Expresiones diferidas](lazy-expressions.md)|Describe las expresiones diferidas, que son cálculos que no se evalúan de inmediato sino cuando realmente se necesita el resultado.|
|[Expresiones de cálculo](computation-expressions.md)|Describe las expresiones de cálculo en F#, que proporcionan una sintaxis adecuada para escribir cálculos que se pueden secuenciar y combinar mediante enlaces y construcciones de flujo de control. Se pueden usar para proporcionar una sintaxis apropiada para los *monads*, una característica de programación funcional que se puede usar para administrar datos, controles y efectos secundarios en programas funcionales. Uno de los tipos de expresión de cálculo, el flujo de trabajo asincrónico, proporciona compatibilidad con los cálculos asincrónicos y en paralelo. Para más información, vea [Flujos de trabajo asincrónicos](asynchronous-workflows.md).|
|[Flujos de trabajo asincrónicos](asynchronous-workflows.md)|Describe los flujos de trabajo asincrónicos, una característica del lenguaje que permite escribir código asincrónico de manera muy similar a cómo se escribe código sincrónico.|
|[Expresiones de código delimitadas](code-quotations.md)|Describe las expresiones de código delimitadas, una característica del lenguaje que permite generar expresiones de código de F# y trabajar con ellas mediante programación.|
|[Expresiones de consulta](query-expressions.md)|Describe las expresiones de consulta, una característica del lenguaje que implementa LINQ para F# y permite escribir consultas para un origen de datos o una colección enumerable.|

## <a name="compiler-supported-constructs"></a>Construcciones admitidas por el compilador

En la tabla siguiente se muestran los temas que describen las construcciones especiales admitidas por el compilador.

|Tema|Descripción|
|-----|-----------|
|[Opciones del compilador](compiler-options.md)|Describe las opciones de línea de comandos para el compilador de F#.|
|[Directivas de compilador](compiler-directives.md)|Describe las directivas de procesador y las directivas de compilador.|
|[Identificadores de línea, archivo y ruta de acceso de origen](source-line-file-path-identifiers.md)|Describe los identificadores `__LINE__`, `__SOURCE_DIRECTORY__` y `__SOURCE_FILE__`, que son valores integrados que permiten obtener acceso al número de línea y al nombre de directorio y archivo de origen en el código.|
