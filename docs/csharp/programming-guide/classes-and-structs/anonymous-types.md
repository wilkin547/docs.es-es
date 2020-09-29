---
title: 'Tipos anónimos: Guía de programación de C#'
description: Los tipos anónimos de C# encapsulan un conjunto de propiedades de solo lectura en un objeto sin necesidad de definir un tipo de forma explícita. El compilador genera un nombre.
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#]
- C# Language, anonymous types
ms.assetid: 59c9d7a4-3b0e-475e-b620-0ab86c088e9b
ms.openlocfilehash: f60c1ea4f3f029ec3b81a4197a711523ec372df9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186164"
---
# <a name="anonymous-types-c-programming-guide"></a>Tipos anónimos (Guía de programación de C#)

Los tipos anónimos son una manera cómoda de encapsular un conjunto de propiedades de solo lectura en un único objeto sin tener que definir primero un tipo explícitamente. El compilador genera el nombre del tipo y no está disponible en el nivel de código fuente. El compilador deduce el tipo de cada propiedad.  
  
 Para crear tipos anónimos, use el operador [new](../../language-reference/operators/new-operator.md) con un inicializador de objeto. Para obtener más información sobre los inicializadores de objeto, vea [Inicializadores de objeto y colección (Guía de programación de C#)](./object-and-collection-initializers.md).  
  
 En el ejemplo siguiente se muestra un tipo anónimo que se inicializa con dos propiedades llamadas `Amount` y `Message`.  
  
```csharp  
var v = new { Amount = 108, Message = "Hello" };  
  
// Rest the mouse pointer over v.Amount and v.Message in the following  
// statement to verify that their inferred types are int and string.  
Console.WriteLine(v.Amount + v.Message);  
```  
  
 Los tipos anónimos suelen usarse en la cláusula [select](../../language-reference/keywords/select-clause.md) de una expresión de consulta para devolver un subconjunto de las propiedades de cada objeto en la secuencia de origen. Para más información sobre las consultas, vea [LINQ en C#](../../linq/index.md).  
  
 Los tipos anónimos contienen una o varias propiedades públicas de solo lectura. No es válido ningún otro tipo de miembros de clase, como métodos o eventos. La expresión que se usa para inicializar una propiedad no puede ser `null`, una función anónima o un tipo de puntero.  
  
 El escenario más habitual es inicializar un tipo anónimo con propiedades de otro tipo. En el siguiente ejemplo, se da por hecho que existe una clase con el nombre `Product`. La clase `Product` incluye las propiedades `Color` y `Price`, junto con otras propiedades que no son de su interés. La variable `products` es una colección de objetos `Product`. La declaración de tipo anónimo comienza con la palabra clave `new`. La declaración inicializa un nuevo tipo que solo usa dos propiedades de `Product`. Esto hace que la consulta devuelva una cantidad de datos menor.  
  
 Si no especifica los nombres de miembro en el tipo anónimo, el compilador da a los miembros de tipo anónimo el mismo nombre que la propiedad que se usa para inicializarlos. Debe proporcionar un nombre para una propiedad que se está inicializando con una expresión, como se muestra en el ejemplo anterior. En el siguiente ejemplo, los nombres de las propiedades del tipo anónimo son `Color` y `Price`.  
  
 [!code-csharp[csRef30Features#81](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csRef30Features/CS/csref30.cs#81)]  
  
 Normalmente, cuando se usa un tipo anónimo para inicializar una variable, la variable se declara como variable local con tipo implícito mediante [var](../../language-reference/keywords/var.md). El nombre del tipo no se puede especificar en la declaración de la variable porque solo el compilador tiene acceso al nombre subyacente del tipo anónimo. Para obtener más información sobre `var`, vea [Variables locales con asignación implícita de tipos](./implicitly-typed-local-variables.md).  
  
 Puede crear una matriz de elementos con tipo anónimo combinando una variable local con tipo implícito y una matriz con tipo implícito, como se muestra en el ejemplo siguiente.  
  
```csharp  
var anonArray = new[] { new { name = "apple", diam = 4 }, new { name = "grape", diam = 1 }};  
```  
  
## <a name="remarks"></a>Comentarios  

 Los tipos anónimos son tipos [class](../../language-reference/keywords/class.md) que derivan directamente de [object](../../language-reference/builtin-types/reference-types.md) y que no se pueden convertir a ningún tipo excepto [object](../../language-reference/builtin-types/reference-types.md). El compilador proporciona un nombre para cada tipo anónimo, aunque la aplicación no pueda acceder a él. Desde el punto de vista de Common Language Runtime, un tipo anónimo no es diferente de otros tipos de referencia.  
  
 Si dos o más inicializadores de objeto anónimo en un ensamblado especifican una secuencia de propiedades que están en el mismo orden y que tienen los mismos nombres y tipos, el compilador trata el objeto como instancias del mismo tipo. Comparten la misma información de tipo generada por el compilador.  
  
 No se puede declarar que un campo, una propiedad, un evento o el tipo de valor devuelto de un método tengan un tipo anónimo. De forma similar, no se puede declarar que un parámetro formal de un método, propiedad, constructor o indizador tenga un tipo anónimo. Para pasar un tipo anónimo, o una colección que contiene tipos anónimos, como un argumento a un método, puede declarar el parámetro como objeto de tipo. Sin embargo, al hacerlo se invalida el propósito del tipado fuerte. Si tiene que almacenar resultados de consulta o pasarlos fuera del límite del método, considere la posibilidad de usar un struct o una clase con nombre normal en lugar de un tipo anónimo.  
  
 Como los métodos <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A> de tipos anónimos se definen en términos de los métodos `Equals` y `GetHashCode` de las propiedades, dos instancias del mismo tipo anónimo son iguales solo si todas sus propiedades son iguales.  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Inicializadores de objeto y colección](./object-and-collection-initializers.md)
- [Introducción a LINQ en C#](../concepts/linq/index.md)
- [LINQ en C#](../../linq/index.md)
