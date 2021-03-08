---
title: Un paseo por C# - Guía de C#
description: ¿Nuevo en C#? Conozca los conceptos básicos del lenguaje. Comience con esta información general.
ms.date: 01/28/2021
ms.openlocfilehash: b58aed5e75be8c71df295506480a2d97c22675aa
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104918"
---
# <a name="a-tour-of-the-c-language"></a>Paseo por el lenguaje C#

C# (pronunciado "si sharp" en inglés) es un lenguaje de programación moderno, basado en objetos y con seguridad de tipos. que permite a los desarrolladores crear muchos tipos de aplicaciones seguras y sólidas que se ejecutan en el ecosistema de .NET. C# tiene sus raíces en la familia de lenguajes C, y a los programadores de C, C++, Java y JavaScript les resultará familiar inmediatamente. Este paseo proporciona información general de los principales componentes del lenguaje en C# 8 y versiones anteriores. Si quiere explorar el lenguaje a través de ejemplos interactivos, pruebe los tutoriales de [introducción a C#](./tutorials/index.md).

C# es un lenguaje de programación ***orientado a componentes***, orientado a objetos. C# proporciona construcciones de lenguaje para admitir directamente estos conceptos, por lo que se trata de un lenguaje natural en el que crear y usar componentes de software. Desde su origen, C# ha agregado características para admitir nuevas cargas de trabajo y prácticas de diseño de software emergentes.

Varias características de C# facilitan la creación de aplicaciones sólidas y duraderas. La [***recolección de elementos no utilizados** _](../../standard/garbage-collection/index.md) reclama de forma automática la memoria ocupada por objetos no utilizados inalcanzables. Los [_*_tipos que aceptan valores NULL_*_](../nullable-references.md) ofrecen protección ante variables que no hacen referencia a objetos asignados. El [_*_control de excepciones_*_](../programming-guide/exceptions/index.md) proporciona un enfoque estructurado y extensible para la detección y recuperación de errores. Las [_*_expresiones lambda_*_](../language-reference/operators/lambda-expressions.md) admiten técnicas de programación funcional. La sintaxis de [_*_Language Integrated Query (LINQ)_*_](../linq/index.md) crea un patrón común para trabajar con datos de cualquier origen. La compatibilidad del lenguaje con las [_*_operaciones asincrónicas_*_](../programming-guide/concepts/async/index.md) proporciona la sintaxis para crear sistemas distribuidos. C# tiene un [_ *_sistema de tipos unificados_**](../programming-guide/types/index.md). Todos los tipos de C#, incluidos los tipos primitivos como `int` y `double`, se heredan de un único tipo `object` raíz. Todos los tipos comparten un conjunto de operaciones comunes. Los valores de cualquier tipo se pueden almacenar, transportar y operar de forma coherente. Además, C# admite tanto [tipos de referencia](../language-reference/builtin-types/reference-types.md) definidos por el usuario como [tipos de valor](../language-reference/builtin-types/value-types.md). C# permite la asignación dinámica de objetos y el almacenamiento en línea de estructuras ligeras. C# admite métodos y tipos genéricos, que proporcionan una mayor seguridad de tipos, así como un mejor rendimiento. C# también proporciona iteradores, gracias a los que los implementadores de clases de colecciones pueden definir comportamientos personalizados para el código de cliente.

C# resalta el ***control de versiones*** para asegurarse de que los programas y las bibliotecas pueden evolucionar con el tiempo de manera compatible. Los aspectos del diseño de C# afectados directamente por las consideraciones de versionamiento incluyen los modificadores `virtual` y `override` independientes, las reglas para la resolución de sobrecargas de métodos y la compatibilidad para declaraciones explícitas de miembros de interfaz.

## <a name="net-architecture"></a>Arquitectura de .NET

Los programas de C# se ejecutan en .NET, un sistema de ejecución virtual denominado Common Language Runtime (CLR) y un conjunto de bibliotecas de clases. CLR es la implementación de Microsoft del estándar internacional Common Language Infrastructure (CLI). CLI es la base para crear entornos de ejecución y desarrollo en los que los lenguajes y las bibliotecas funcionan juntos sin problemas.

El código fuente escrito en C# se compila en un [lenguaje intermedio (IL)](../../standard/managed-code.md) que guarda conformidad con la especificación de CLI. El código y los recursos de IL, como los mapas de bits y las cadenas, se almacenan en un ensamblado, normalmente con una extensión *.dll*. Un ensamblado contiene un manifiesto que proporciona información sobre los tipos, la versión y la referencia cultural.

Cuando se ejecuta el programa C#, el ensamblado se carga en CLR. CLR realiza la compilación Just-In-Time (JIT) para convertir el código IL en instrucciones de máquina nativas. Además, CLR proporciona otros servicios relacionados con la recolección de elementos no utilizados, el control de excepciones y la administración de recursos. El código que se ejecuta en el CLR se conoce a veces como "código administrado", a diferencia del "código no administrado", que se compila en un lenguaje nativo de la máquina destinado a un sistema específico.

La interoperabilidad entre lenguajes es una característica principal de .NET. El código IL generado por el compilador de C# se ajusta a la especificación de tipo común (CTS). El código IL generado desde C# puede interactuar con el código generado a partir de las versiones de .NET de F# , Visual Basic, C++ o cualquiera de los más de 20 lenguajes compatibles con CTS. Un solo ensamblado puede contener varios módulos escritos en diferentes lenguajes .NET y los tipos se pueden hacer referencia mutuamente igual que si estuvieran escritos en el mismo lenguaje.

Además de los servicios en tiempo de ejecución, .NET también incluye amplias bibliotecas, que admiten muchas cargas de trabajo diferentes. Se organizan en espacios de nombres que proporcionan una gran variedad de funciones útiles para todo, desde la entrada y salida de archivos, la manipulación de cadenas y el análisis de XML hasta los marcos de aplicaciones web y los controles de Windows Forms. En una aplicación de C# típica se usa la biblioteca de clases de .NET de forma extensa para controlar tareas comunes de infraestructura.

Para obtener más información sobre .NET, vea [Introducción a .NET](../../core/introduction.md).

## <a name="hello-world"></a>Hola a todos

El programa "Hola mundo" tradicionalmente se usa para presentar un lenguaje de programación. En este caso, se usa C#:

:::code language="csharp" interactive="try-dotnet" source="./snippets/shared/HelloWorld.cs":::

El programa "Hola mundo" empieza con una directiva `using` que hace referencia al espacio de nombres `System`. Los espacios de nombres proporcionan un método jerárquico para organizar las bibliotecas y los programas de C#. Los espacios de nombres contienen tipos y otros espacios de nombres; por ejemplo, el espacio de nombres `System` contiene varios tipos, como la clase `Console` a la que se hace referencia en el programa, y otros espacios de nombres, como `IO` y `Collections`. Una directiva `using` que hace referencia a un espacio de nombres determinado permite el uso no calificado de los tipos que son miembros de ese espacio de nombres. Debido a la directiva `using`, puede utilizar el programa `Console.WriteLine` como abreviatura de `System.Console.WriteLine`.

La clase `Hello` declarada por el programa "Hola mundo" tiene un miembro único, el método llamado `Main`. El método `Main` se declara con el modificador `static`. Mientras que los métodos de instancia pueden hacer referencia a una instancia de objeto envolvente determinada utilizando la palabra clave `this`, los métodos estáticos funcionan sin referencia a un objeto determinado. Por convención, un método estático denominado `Main` sirve como punto de entrada de un programa de C#.

La salida del programa la genera el método `WriteLine` de la clase `Console` en el espacio de nombres `System`. Esta clase la proporcionan las bibliotecas de clase estándar, a las que, de forma predeterminada, el compilador hace referencia automáticamente.

## <a name="types-and-variables"></a>Tipos y variables

Hay dos clases de tipos en C#: *tipos de valor* y *tipos de referencia*. Las variables de tipos de valor contienen directamente sus datos. Las variables de tipos de referencia almacenan referencias a los datos, lo que se conoce como objetos. Con los tipos de referencia, es posible que dos variables hagan referencia al mismo objeto y que, por tanto, las operaciones en una variable afecten al objeto al que hace referencia la otra. Con los tipos de valor, cada variable tiene su propia copia de los datos y no es posible que las operaciones en una variable afecten a la otra (excepto para las variables de parámetro `ref` y `out`).

Un ***identificador*** es un nombre de variable. Un identificador es una secuencia de caracteres Unicode sin ningún espacio en blanco. Un identificador puede ser una palabra reservada de C# si tiene el prefijo `@`. El uso de una palabra reservada como identificador puede ser útil al interactuar con otros lenguajes.

Los tipos de valor de C# se dividen en *tipos simples*, *tipos de enumeración*, *tipos de estructura*, *tipos de valor que aceptan valores NULL* y *tipos de valor de tupla*. Los tipos de referencia de C# se dividen en *tipos de clase*, *tipos de interfaz*, *tipos de matriz* y *tipos delegados*.

En el esquema siguiente se ofrece información general del sistema de tipos de C#.

- [Tipos de valor](../language-reference/builtin-types/value-types.md)
  - [Tipos simples](../language-reference/builtin-types/value-types.md#built-in-value-types)
    - [Entero con signo](../language-reference/builtin-types/integral-numeric-types.md): `sbyte`, `short`, `int`, `long`
    - [Entero sin signo](../language-reference/builtin-types/integral-numeric-types.md): `byte`, `ushort`, `uint`, `ulong`
    - [Caracteres Unicode](../../standard/base-types/character-encoding-introduction.md): `char`, que representa una unidad de código UTF-16
    - [Punto flotante binario IEEE](../language-reference/builtin-types/floating-point-numeric-types.md): `float`, `double`
    - [Punto flotante decimal de alta precisión](../language-reference/builtin-types/floating-point-numeric-types.md): `decimal`
    - Booleano: `bool`, que representa valores booleanos, valores que son `true` o `false`
  - [Tipos de enumeración](../language-reference/builtin-types/enum.md)
    - Tipos definidos por el usuario con el formato `enum E {...}`. Un tipo `enum` es un tipo distinto con constantes con nombre. Cada tipo `enum` tiene un tipo subyacente, que debe ser uno de los ocho tipos enteros. El conjunto de valores de un tipo `enum` es igual que el conjunto de valores del tipo subyacente.
  - [Tipos de estructura](../language-reference/builtin-types/struct.md)
    - Tipos definidos por el usuario con el formato `struct S {...}`
  - [Tipos de valores que aceptan valores NULL](../language-reference/builtin-types/nullable-value-types.md)
    - Extensiones de todos los demás tipos de valor con un valor `null`
  - [Tipos de valor de tupla](../language-reference/builtin-types/value-tuples.md)
    - Tipos definidos por el usuario con el formato `(T1, T2, ...)`
- [Tipos de referencia](../language-reference/keywords/reference-types.md)
  - [Tipos de clase](../language-reference/keywords/class.md)
    - Clase base definitiva de todos los demás tipos: `object`
    - [Cadenas Unicode](../../standard/base-types/character-encoding-introduction.md): `string`, que representa una secuencia de unidades de código UTF-16
    - Tipos definidos por el usuario con el formato `class C {...}`
  - [Tipos de interfaz](../language-reference/keywords/interface.md)
    - Tipos definidos por el usuario con el formato `interface I {...}`
  - [Tipos de matriz](../programming-guide/arrays/index.md)
    - Unidimensional, multidimensional y escalonada. Por ejemplo, `int[]`, `int[,]` y `int[][]`.
  - [Tipos delegados](../language-reference/builtin-types/reference-types.md#the-delegate-type)
    - Tipos definidos por el usuario con el formato `delegate int D(...)`

Los programas de C# utilizan *declaraciones de tipos* para crear nuevos tipos. Una declaración de tipos especifica el nombre y los miembros del nuevo tipo. Seis de las categorías de tipos de C# las define el usuario: tipos de clase, tipos de estructura, tipos de interfaz, tipos de enumeración, tipos de delegado y tipos de valor de tupla.

- A tipo `class` define una estructura de datos que contiene miembros de datos (campos) y miembros de función (métodos, propiedades y otros). Los tipos de clase admiten herencia única y polimorfismo, mecanismos por los que las clases derivadas pueden extender y especializar clases base.
- Un tipo `struct` es similar a un tipo de clase, por el hecho de que representa una estructura con miembros de datos y miembros de función. Pero a diferencia de las clases, las estructuras son tipos de valor y no suelen requerir la asignación del montón. Los tipos de estructura no admiten la herencia especificada por el usuario y todos se heredan implícitamente del tipo `object`.
- Un tipo `interface` define un contrato como un conjunto con nombre de miembros públicos. Un valor `class` o `struct` que implementa `interface` debe proporcionar implementaciones de miembros de la interfaz. Un `interface` puede heredar de varias interfaces base, y un `class` o `struct` pueden implementar varias interfaces.
- Un tipo `delegate` representa las referencias a métodos con una lista de parámetros determinada y un tipo de valor devuelto. Los delegados permiten tratar métodos como entidades que se puedan asignar a variables y se puedan pasar como parámetros. Los delegados son análogos a los tipos de función proporcionados por los lenguajes funcionales. También son similares al concepto de punteros de función de otros lenguajes. A diferencia de los punteros de función, los delegados están orientados a objetos y tienen seguridad de tipos.

Los tipos `class`, `struct`, `interface` y `delegate` admiten parámetros genéricos, mediante los que se pueden parametrizar con otros tipos.

C# admite matrices unidimensionales y multidimensionales de cualquier tipo. A diferencia de los tipos enumerados antes, no es necesario declarar los tipos de matriz antes de usarlos. En su lugar, los tipos de matriz se crean mediante un nombre de tipo entre corchetes. Por ejemplo, `int[]` es una matriz unidimensional de `int`, `int[,]` es una matriz bidimensional de `int` y `int[][]` es una matriz unidimensional de las matrices unidimensionales, o la matriz "escalonada", de `int`.

Los tipos que aceptan valores NULL no requieren una definición independiente. Para cada tipo `T` que no acepta valores NULL, existe un tipo `T?` que acepta valores NULL correspondiente, que puede tener un valor adicional, `null`. Por ejemplo, `int?` es un tipo que puede contener cualquier entero de 32 bits o el valor `null` y `string?` es un tipo que puede contener cualquier `string` o el valor `null`.

El sistema de tipos de C# está unificado, de tal forma que un valor de cualquier tipo puede tratarse como `object`. Todos los tipos de C# directa o indirectamente se derivan del tipo de clase `object`, y `object` es la clase base definitiva de todos los tipos. Los valores de tipos de referencia se tratan como objetos mediante la visualización de los valores como tipo `object`. Los valores de tipos de valor se tratan como objetos mediante la realización de *operaciones de conversión boxing* y *operaciones de conversión unboxing*. En el ejemplo siguiente, un valor `int` se convierte en `object` y vuelve a `int`.

:::code language="csharp" source="./snippets/shared/Program.cs" ID="boxing" :::

Cuando se asigna un valor de un tipo de valor a una referencia `object`, se asigna un "box" para contener el valor. Ese box es una instancia de un tipo de referencia, y es donde se copia el valor. Por el contrario, cuando una referencia `object` se convierte en un tipo de valor, se comprueba si el elemento `object` al que se hace referencia es un box del tipo de valor correcto. Si la comprobación se realiza correctamente, el valor del box se copia en el tipo de valor.

El sistema de tipos unificado de C# conlleva efectivamente que los tipos de valor se tratan como referencias `object` "a petición". Debido a la unificación, las bibliotecas de uso general que utilizan el tipo `object` pueden usarse con todos los tipos que se derivan de `object`, como, por ejemplo, los tipos de referencia y los tipos de valor.

Hay varios tipos de *variables* en C#, entre otras, campos, elementos de matriz, variables locales y parámetros. Las variables representan ubicaciones de almacenamiento. Cada variable tiene un tipo que determina qué valores se pueden almacenar en ella, como se muestra a continuación.

- Tipo de valor distinto a NULL
  - Un valor de ese tipo exacto
- Tipos de valor NULL
  - Un valor `null` o un valor de ese tipo exacto
- objeto
  - Una referencia `null`, una referencia a un objeto de cualquier tipo de referencia o una referencia a un valor de conversión boxing de cualquier tipo de valor
- Tipo de clase
  - Una referencia `null`, una referencia a una instancia de ese tipo de clase o una referencia a una instancia de una clase derivada de ese tipo de clase
- Tipo de interfaz
  - Un referencia `null`, una referencia a una instancia de un tipo de clase que implementa dicho tipo de interfaz o una referencia a un valor de conversión boxing de un tipo de valor que implementa dicho tipo de interfaz
- Tipo de matriz
  - Una referencia `null`, una referencia a una instancia de ese tipo de matriz o una referencia a una instancia de un tipo de matriz compatible
- Tipo delegado
  - Una referencia `null` o una referencia a una instancia de un tipo delegado compatible

## <a name="program-structure"></a>Estructura del programa

Los conceptos organizativos clave de C# son [***programas** _](../programming-guide/inside-a-program/index.md), [_*_espacios de nombres_*_](../programming-guide/namespaces/index.md), [_*_tipos_*_](../programming-guide/types/index.md), [_*_miembros_*_](../programming-guide/classes-and-structs/members.md) y [_*_ensamblados_*_](../../standard/assembly/index.md). Los programas declaran tipos, que contienen miembros y pueden organizarse en espacios de nombres. Las clases, estructuras e interfaces son ejemplos de tipos. Los campos, los métodos, las propiedades y los eventos son ejemplos de miembros. Cuando se compilan programas de C#, se empaquetan físicamente en ensamblados. Normalmente, los ensamblados tienen la extensión de archivo `.exe` o `.dll`, en función de si implementan _*_aplicaciones_*_ o _*_bibliotecas_**, respectivamente.

Como ejemplo pequeño, considere la posibilidad de usar un ensamblado que contenga el código siguiente:

:::code language="csharp" source="./snippets/shared/AcmeStack.cs":::

El nombre completo de esta clase es `Acme.Collections.Stack`. La clase contiene varios miembros: un campo denominado `top`, dos métodos denominados `Push` y `Pop`, y una clase anidada denominada `Entry`. La clase `Entry` contiene además tres miembros: un campo denominado `next`, un campo denominado `data` y un constructor. `Stack` es una clase *genérica*. Tiene un parámetro de tipo, `T`, que se reemplaza con un tipo concreto cuando se usa.

> [!NOTE]
> Una *pila* es una colección de tipo "el primero que entra es el último que sale" (FILO). Los elementos nuevos se agregan a la parte superior de la pila. Cuando se quita un elemento, se quita de la parte superior de la pila.

Los ensamblados contienen código ejecutable en forma de instrucciones de lenguaje intermedio (IL) e información simbólica en forma de metadatos. Antes de ejecutarlo, el compilador Just-In-Time (JIT) del entorno de ejecución de .NET convierte el código de IL de un ensamblado en código específico del procesador.

Como un ensamblado es una unidad autodescriptiva de funcionalidad que contiene código y metadatos, no hay necesidad de directivas `#include` ni archivos de encabezado de C#. Los tipos y miembros públicos contenidos en un ensamblado determinado estarán disponibles en un programa de C# simplemente haciendo referencia a dicho ensamblado al compilar el programa. Por ejemplo, este programa usa la clase `Acme.Collections.Stack` desde el ensamblado `acme.dll`:

:::code language="csharp" source="./snippets/shared/StackUsage.cs":::

Para compilar este programa, necesitaría *hacer referencia* al ensamblado que contiene la clase de pila que se define en el ejemplo anterior.

Los programas de C# se pueden almacenar en varios archivos de origen. Cuando se compila un programa de C#, todos los archivos de origen se procesan juntos y se pueden hacer referencia entre sí de manera libre. Conceptualmente, es como si todos los archivos de origen estuviesen concatenados en un archivo de gran tamaño antes de que se procesen. En C# nunca se necesitan declaraciones adelantadas porque, excepto en contadas ocasiones, el orden de declaración es insignificante. C# no limita un archivo de origen a declarar solamente un tipo público ni precisa que el nombre del archivo de origen coincida con un tipo declarado en el archivo de origen.

En otros artículos de este paseo se explican estos bloques organizativos.

>[!div class="step-by-step"]
>[Siguiente](types.md)
