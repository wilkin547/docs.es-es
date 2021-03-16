---
title: 'Tipos básicos: Guía de C#'
description: Obtenga información sobre los tipos principales (valores numéricos, cadenas y objeto) en todos los programas de C#
ms.date: 10/10/2016
ms.technology: csharp-fundamentals
ms.assetid: 95c686ba-ae4f-440e-8e94-0dbd6e04d11f
ms.openlocfilehash: 1c3cdefe6aba300536386fe4bb66d788814bcd9d
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258187"
---
# <a name="types-variables-and-values"></a>Tipos, variables y valores

C# es un lenguaje fuertemente tipado. Todas las variables y constantes tienen un tipo, al igual que todas las expresiones que se evalúan como un valor. Cada una de las firmas de método especifica un tipo para cada parámetro de entrada y para el valor devuelto. La biblioteca de clases .NET define un conjunto de tipos numéricos integrados, así como tipos más complejos que representan una amplia variedad de construcciones lógicas, como el sistema de archivos, conexiones de red, colecciones y matrices de objetos, y fechas. Los programas de C# típicos usan tipos de la biblioteca de clases, así como tipos definidos por el usuario que modelan los conceptos que son específicos del dominio del problema del programa.  
  
Entre la información almacenada en un tipo se puede incluir lo siguiente:  
  
- El espacio de almacenamiento que requiere una variable del tipo.  
  
- Los valores máximo y mínimo que puede representar.  
  
- Los miembros (métodos, campos, eventos, etc.) que contiene.  
  
- El tipo base del que hereda.

- Interfaces que implementa.

- La ubicación donde se asignará la memoria para variables en tiempo de ejecución.  
  
- Los tipos de operaciones permitidas.  
  
El compilador usa información de tipo para garantizar que todas las operaciones que se realizan en el código cuentan *con seguridad de tipos*. Por ejemplo, si declara una variable de tipo [int](language-reference/builtin-types/integral-numeric-types.md), el compilador le permite usar la variable en operaciones de suma y resta. Si intenta realizar esas mismas operaciones en una variable de tipo [bool](language-reference/builtin-types/bool.md), el compilador genera un error, como se muestra en el siguiente ejemplo:  
  
[!code-csharp[Type Safety](../../samples/snippets/csharp/concepts/basic-types/type-safety.cs)]  
  
> [!NOTE]  
> Los desarrolladores de C y C++ deben tener en cuenta que, en C#, [bool](language-reference/builtin-types/bool.md) no se puede convertir en [int](language-reference/builtin-types/integral-numeric-types.md).  
  
El compilador inserta la información de tipo en el archivo ejecutable como metadatos. Common Language Runtime (CLR) usa esos metadatos en tiempo de ejecución para garantizar aún más la seguridad de tipos cuando asigna y reclama memoria.  

## <a name="specifying-types-in-variable-declarations"></a>Especificar tipos en declaraciones de variable

Cuando declare una variable o constante en un programa, debe especificar su tipo o usar la palabra clave [var](language-reference/keywords/var.md) para que el compilador infiera el tipo. En el ejemplo siguiente se muestran algunas declaraciones de variable que utilizan tanto tipos numéricos integrados como tipos complejos definidos por el usuario:  
  
[!code-csharp[Variable Declaration](../../samples/snippets/csharp/concepts/basic-types/variable-declaration.cs)]  
  
Los tipos de parámetros de método y valores devueltos se especifican en la firma del método. En la siguiente firma se muestra un método que requiere una variable [int](language-reference/builtin-types/integral-numeric-types.md) como argumento de entrada y devuelve una cadena:  
  
[!code-csharp[Method Signature](../../samples/snippets/csharp/concepts/basic-types/method-signature.cs)]  
  
Tras declarar una variable, no se puede volver a declarar con un nuevo tipo y no se le puede asignar un valor que no sea compatible con su tipo declarado. Por ejemplo, no puede declarar un valor [int](language-reference/builtin-types/integral-numeric-types.md) y, luego, asignarle un valor booleano de `true`. En cambio, los valores se pueden convertir en otros tipos, por ejemplo, cuando se asignan a variables nuevas o se pasan como argumentos de método. El compilador realiza automáticamente una *conversión de tipo* que no da lugar a una pérdida de datos. Una conversión que pueda dar lugar a la pérdida de datos requiere un valor *cast* en el código fuente.

Para obtener más información, consulte [Conversiones de tipos](programming-guide/types/casting-and-type-conversions.md).

## <a name="built-in-types"></a>Tipos integrados

C# proporciona un conjunto estándar de tipos numéricos integrados para representar números enteros, valores de punto flotante, expresiones booleanas, caracteres de texto, valores decimales y otros tipos de datos. También hay tipos **string** y **object** integrados. Están disponibles para su uso en cualquier programa de C#. Para obtener una lista completa de los tipos integrados, vea [Tipos integrados](language-reference/builtin-types/built-in-types.md).
  
## <a name="custom-types"></a>Tipos personalizados

Las construcciones [struct](language-reference/builtin-types/struct.md), [class](language-reference/keywords/class.md), [record](language-reference/builtin-types/record.md), [interface](language-reference/keywords/interface.md) y [enum](language-reference/builtin-types/enum.md) se utilizan para crear sus propios tipos personalizados. La biblioteca de clases .NET es en sí misma una colección de tipos personalizados proporcionados por Microsoft que puede usar en sus propias aplicaciones. De forma predeterminada, los tipos usados con más frecuencia en la biblioteca de clases están disponibles en cualquier programa de C#. Otros están disponibles solo cuando agrega explícitamente una referencia de proyecto al ensamblado en el que se definen. Una vez que el compilador tenga una referencia al ensamblado, puede declarar variables (y constantes) de los tipos declarados en dicho ensamblado en el código fuente.
  
## <a name="generic-types"></a>Tipos genéricos

Los tipos se pueden declarar con uno o varios *parámetros de tipo* que actúan como un marcador de posición para el tipo real (el *tipo concreto*) que proporcionará el código de cliente cuando cree una instancia del tipo. Estos tipos se denominan *tipos genéricos*. Por ejemplo, <xref:System.Collections.Generic.List%601> tiene un parámetro de tipo al que, por convención, se le denomina *T*. Cuando crea una instancia del tipo, especifica el tipo de los objetos que contendrá la lista, por ejemplo, la cadena:  
  
[!code-csharp[Generic types](../../samples/snippets/csharp/concepts/basic-types/generic-type.cs)]
  
El uso del parámetro de tipo permite reutilizar la misma clase para incluir cualquier tipo de elemento, sin necesidad de convertir cada elemento en [object](language-reference/builtin-types/reference-types.md#the-object-type). Las clases de colección genéricas se denominan *colecciones fuertemente tipadas* porque el compilador conoce el tipo específico de los elementos de la colección y puede generar un error en tiempo de compilación si, por ejemplo, intenta agregar un valor entero al objeto `strings` del ejemplo anterior. Para más información, vea [Genéricos](programming-guide/generics/index.md).

## <a name="implicit-types-anonymous-types-and-tuple-types"></a>Tipos implícitos, tipos anónimos y tipos de tupla

Como se ha mencionado anteriormente, puede asignar implícitamente un tipo a una variable local (pero no miembros de clase) mediante la palabra clave [var](language-reference/keywords/var.md). La variable sigue recibiendo un tipo en tiempo de compilación, pero este lo proporciona el compilador. Para obtener más información, consulte [Variables locales con asignación implícita de tipos](programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
En algunos casos, resulta conveniente crear un tipo con nombre para conjuntos sencillos de valores relacionados que no quiera almacenar ni pasar fuera de los límites del método. Puede crear *tipos anónimos* para este fin. Para obtener más información, consulte [Tipos anónimos (Guía de programación de C#)](programming-guide/classes-and-structs/anonymous-types.md).

Es habitual querer devolver más de un valor de un método. Puede crear *tipos de tupla* que devuelven varios valores en una única llamada de método. Para obtener más información, consulte [Tipos de tupla](language-reference/builtin-types/value-tuples.md).

## <a name="the-common-type-system"></a>Common Type System

Es importante entender dos aspectos fundamentales sobre el sistema de tipos en .NET:  
  
- Es compatible con el principio de herencia. Los tipos pueden derivarse de otros tipos, denominados *tipos base*. El tipo derivado hereda (con algunas restricciones), los métodos, las propiedades y otros miembros del tipo base. A su vez, el tipo base puede derivarse de algún otro tipo, en cuyo caso el tipo derivado hereda los miembros de ambos tipos base en su jerarquía de herencia. Todos los tipos, incluidos los tipos numéricos integrados como <xref:System.Int32> (palabra clave de C#: `int`), se derivan en última instancia de un único tipo base, que es <xref:System.Object> (palabra clave de C#: `object`). Esta jerarquía de tipos unificada se denomina [Common Type System](../standard/common-type-system.md) (CTS). Para obtener más información sobre la herencia en C#, consulte [Herencia](programming-guide/classes-and-structs/inheritance.md).  
  
- En CTS, cada tipo se define como un *tipo de valor* o un *tipo de referencia*. Esto incluye todos los tipos personalizados de la biblioteca de clases .NET y también sus propios tipos definidos por el usuario. Los tipos que se definen mediante la palabra clave `struct` o `enum` son tipos de valor. Para más información sobre los tipos de valor, vea [Tipos de valor](language-reference/builtin-types/value-types.md). Los tipos que se definen mediante el uso de la palabra clave [class](language-reference/keywords/class.md) son tipos de referencia. Para obtener más información sobre los tipos de referencia, consulte [Classes](programming-guide/classes-and-structs/classes.md) (Clases). Los tipos de referencia y los tipos de valor tienen distintas reglas de tiempo de compilación y distintos comportamientos de tiempo de ejecución.

## <a name="see-also"></a>Vea también

- [Tipos de estructura](language-reference/builtin-types/struct.md)
- [Tipos de enumeración](language-reference/builtin-types/enum.md)
- [Clases](programming-guide/classes-and-structs/classes.md)
