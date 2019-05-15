---
title: 'Introducción a los genéricos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
ms.openlocfilehash: 0d7ecb7f7fd0bb0985234cdc2cf8d37b53323c86
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64595485"
---
# <a name="introduction-to-generics-c-programming-guide"></a>Introducción a los genéricos (Guía de programación de C#)
Las clases y métodos genéricos combinan reusabilidad, seguridad de tipos y eficacia de una manera en que sus homólogos no genéricos no pueden. Los genéricos se usan frecuentemente con colecciones y los métodos que funcionan en ellas. La versión 2.0 de la biblioteca de clases .NET Framework proporciona un nuevo espacio de nombres, <xref:System.Collections.Generic>, que contiene varias clases de colección nuevas basadas en genéricos. Se recomienda que todas las aplicaciones destinadas a .NET Framework 2.0 y versiones posteriores usen las nuevas clases de colección genéricas en lugar de sus homólogas no genéricas anteriores como <xref:System.Collections.ArrayList>. Para más información, vea [Elementos genéricos en .NET](../../../standard/generics/index.md).  
  
 Por supuesto, también se pueden crear tipos y métodos genéricos personalizados para proporcionar soluciones y patrones de diseño generalizados propios con seguridad de tipos y eficaces. En el ejemplo de código siguiente se muestra una clase genérica simple de lista vinculada para fines de demostración. (En la mayoría de los casos, se debe usar la clase <xref:System.Collections.Generic.List%601> proporcionada por la biblioteca de clases .NET Framework en lugar de crear una propia). El parámetro de tipo `T` se usa en diversas ubicaciones donde normalmente se usaría un tipo concreto para indicar el tipo del elemento almacenado en la lista. Se usa de estas formas:  
  
- Como el tipo de un parámetro de método en el método `AddHead`.  
  
- Como el tipo de valor devuelto de la propiedad `Data` en la clase anidada `Node`.  
  
- Como el tipo de miembro privado `data` de la clase anidada.  
  
 Tenga en cuenta que T está disponible para la clase anidada `Node`. Cuando se crea una instancia de `GenericList<T>` con un tipo concreto, por ejemplo como un `GenericList<int>`, cada repetición de `T` se sustituye por `int`.  
  
 [!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]  
  
 En el ejemplo de código siguiente se muestra cómo el código de cliente usa la clase genérica `GenericList<T>` para crear una lista de enteros. Simplemente cambiando el argumento de tipo, el código siguiente puede modificarse fácilmente para crear listas de cadenas o cualquier otro tipo personalizado:  
  
 [!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic>
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Genéricos](../../../csharp/programming-guide/generics/index.md)
