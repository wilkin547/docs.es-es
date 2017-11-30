---
title: "Tipos anónimos (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- anonymous types [C#]
- C# Language, anonymous types
ms.assetid: 59c9d7a4-3b0e-475e-b620-0ab86c088e9b
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 24ebf1c98e14eaf74572a6143ea6865d89735a6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-types-c-programming-guide"></a>Tipos anónimos (Guía de programación de C#)
Los tipos anónimos son una manera cómoda de encapsular un conjunto de propiedades de solo lectura en un único objeto sin tener que definir primero un tipo explícitamente. El compilador genera el nombre del tipo y no está disponible en el nivel de código fuente. El compilador deduce el tipo de cada propiedad.  
  
 Para crear tipos anónimos, use el operador [new](../../../csharp/language-reference/keywords/new.md) con un inicializador de objeto. Para obtener más información sobre los inicializadores de objeto, vea [Inicializadores de objeto y colección (Guía de programación de C#)](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
 En el ejemplo siguiente se muestra un tipo anónimo que se inicializa con dos propiedades llamadas `Amount` y `Message`.  
  
```csharp  
var v = new { Amount = 108, Message = "Hello" };  
  
// Rest the mouse pointer over v.Amount and v.Message in the following  
// statement to verify that their inferred types are int and string.  
Console.WriteLine(v.Amount + v.Message);  
```  
  
 Los tipos anónimos suelen usarse en la cláusula [select](../../../csharp/language-reference/keywords/select-clause.md) de una expresión de consulta para devolver un subconjunto de las propiedades de cada objeto en la secuencia de origen. Para obtener más información sobre consultas, vea [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md).  
  
 Los tipos anónimos contienen una o varias propiedades públicas de solo lectura. No es válido ningún otro tipo de miembros de clase, como métodos o eventos. La expresión que se usa para inicializar una propiedad no puede ser `null`, una función anónima o un tipo de puntero.  
  
 El escenario más habitual es inicializar un tipo anónimo con propiedades de otro tipo. En el siguiente ejemplo, se da por hecho que existe una clase con el nombre `Product`. La clase `Product` incluye las propiedades `Color` y `Price`, junto con otras propiedades que no son de su interés. La variable `products` es una colección de objetos `Product`. La declaración de tipo anónimo comienza con la palabra clave `new`. La declaración inicializa un nuevo tipo que solo usa dos propiedades de `Product`. Esto hace que la consulta devuelva una cantidad de datos menor.  
  
 Si no especifica los nombres de miembro en el tipo anónimo, el compilador da a los miembros de tipo anónimo el mismo nombre que la propiedad que se usa para inicializarlos. Debe proporcionar un nombre para una propiedad que se está inicializando con una expresión, como se muestra en el ejemplo anterior. En el siguiente ejemplo, los nombres de las propiedades del tipo anónimo son `Color` y `Price`.  
  
 [!code-csharp[csRef30Features#81](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/anonymous-types_1.cs)]  
  
 Normalmente, cuando se usa un tipo anónimo para inicializar una variable, la variable se declara como variable local con tipo implícito mediante [var](../../../csharp/language-reference/keywords/var.md). El nombre del tipo no se puede especificar en la declaración de la variable porque solo el compilador tiene acceso al nombre subyacente del tipo anónimo. Para obtener más información sobre `var`, vea [Variables locales con asignación implícita de tipos](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
 Puede crear una matriz de elementos con tipo anónimo combinando una variable local con tipo implícito y una matriz con tipo implícito, como se muestra en el ejemplo siguiente.  
  
```csharp  
var anonArray = new[] { new { name = "apple", diam = 4 }, new { name = "grape", diam = 1 }};  
```  
  
## <a name="remarks"></a>Comentarios  
 Los tipos anónimos son tipos [class](../../../csharp/language-reference/keywords/class.md) que derivan directamente de [object](../../../csharp/language-reference/keywords/object.md) y que no se pueden convertir a ningún tipo excepto [object](../../../csharp/language-reference/keywords/object.md). El compilador proporciona un nombre para cada tipo anónimo, aunque la aplicación no pueda acceder a él. Desde el punto de vista de Common Language Runtime, un tipo anónimo no es diferente de otros tipos de referencia.  
  
 Si dos o más inicializadores de objeto anónimo en un ensamblado especifican una secuencia de propiedades que están en el mismo orden y que tienen los mismos nombres y tipos, el compilador trata el objeto como instancias del mismo tipo. Comparten la misma información de tipo generada por el compilador.  
  
 No se puede declarar que un campo, una propiedad, un evento o el tipo de valor devuelto de un método tengan un tipo anónimo. De forma similar, no se puede declarar que un parámetro formal de un método, propiedad, constructor o indizador tenga un tipo anónimo. Para pasar un tipo anónimo, o una colección que contiene tipos anónimos, como un argumento a un método, puede declarar el parámetro como objeto de tipo. Sin embargo, al hacerlo se invalida el propósito del tipado fuerte. Si tiene que almacenar resultados de consulta o pasarlos fuera del límite del método, considere la posibilidad de usar un struct o una clase con nombre normal en lugar de un tipo anónimo.  
  
 Como los métodos <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A> de tipos anónimos se definen en términos de los métodos `Equals` y `GetHashCode` de las propiedades, dos instancias del mismo tipo anónimo son iguales solo si todas sus propiedades son iguales.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Inicializadores de objeto y colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 [Introducción a LINQ en C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)
