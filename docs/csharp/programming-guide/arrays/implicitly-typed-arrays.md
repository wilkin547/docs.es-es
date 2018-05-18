---
title: Matrices con asignación implícita de tipos (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicity-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: 60d320b233986154c3c51c409bade24d0862dedd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a>Matrices con asignación implícita de tipos (Guía de programación de C#)
Puede crear una matriz con tipo implícito en la que se deduce el tipo de la instancia de matriz de los elementos especificados en el inicializador de matriz. Las reglas de cualquier variable con tipo implícito también se aplican a las matrices con tipo implícito. Para más información, vea [Variables locales con asignación implícita de tipos](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
 Normalmente, se usan matrices con tipo implícito en expresiones de consulta junto con tipos anónimos e inicializadores de objeto y colección.  
  
 En los ejemplos siguientes, se muestra cómo crear una matriz con tipo implícito:  
  
 [!code-csharp[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]  
  
 En el ejemplo anterior observe que, con las matrices con tipo implícito, no se usan corchetes en el lado izquierdo de la instrucción de inicialización. Tenga en cuenta también que las matrices escalonadas se inicializan mediante `new []` al igual que las matrices unidimensionales.  
  
## <a name="implicitly-typed-arrays-in-object-initializers"></a>Matrices con tipo implícito en inicializadores de objeto  
 Al crear un tipo anónimo que contiene una matriz, esta debe tener tipo implícito en el inicializador de objeto del tipo. En el ejemplo siguiente, `contacts` es una matriz con tipos implícitos anónimos, cada uno de los cuales contiene una matriz denominada `PhoneNumbers`. Tenga en cuenta que la palabra clave `var` no se usa dentro de los inicializadores de objeto.  
  
 [!code-csharp[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Variables locales con asignación implícita de tipos](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)  
 [Matrices](../../../csharp/programming-guide/arrays/index.md)  
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [Inicializadores de objeto y colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 [var](../../../csharp/language-reference/keywords/var.md)  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)
