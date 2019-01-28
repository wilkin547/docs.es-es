---
title: 'Ventajas de los genéricos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], benefits
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
ms.openlocfilehash: 9ba4b81db0ea352f82127a838ab6b13f09d259e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650985"
---
# <a name="benefits-of-generics-c-programming-guide"></a>Ventajas de los genéricos (Guía de programación de C#)
Los genéricos proporcionan la solución a una limitación en versiones anteriores de Common Language Runtime y el lenguaje de C# en el que se obtiene la generalización mediante la conversión de tipos a y desde el tipo base universal <xref:System.Object>. Mediante la creación de una clase genérica, puede crear una colección con seguridad de tipos en tiempo de compilación.  
  
 Las limitaciones de usar clases de colección no genéricas pueden mostrarse al escribir un programa corto que use la clase de colección <xref:System.Collections.ArrayList> desde la biblioteca de clases .NET. Una instancia de la clase <xref:System.Collections.ArrayList> puede almacenar cualquier tipo de valor o referencia.  
  
 [!code-csharp[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]  
  
 Pero esta comodidad tiene un precio. Cualquier tipo de valor o referencia que se agregue a <xref:System.Collections.ArrayList> se convierte implícitamente a <xref:System.Object>. Si los elementos son tipos de valor, se les debe aplicar la conversión boxing cuando se agregan a la lista, y se les debe aplicar la conversión unboxing cuando se recuperan. Las operaciones de conversión y de conversión boxing y unboxing disminuyen el rendimiento; el efecto de la conversión boxing y unboxing puede ser muy importante en escenarios donde debe recorrer en iteración colecciones grandes.  
  
 La otra limitación es la falta de comprobación de tipos en tiempo de compilación; como <xref:System.Collections.ArrayList> convierte todo en <xref:System.Object>, no existe ninguna manera en tiempo de compilación de evitar que el código de cliente realice algo como esto:  
  
 [!code-csharp[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]  
  
 Aunque es perfectamente aceptable y a veces intencional si está creando una colección heterogénea, combinar cadenas y `ints` en un <xref:System.Collections.ArrayList> único probablemente se deba a un error de programación, y este error no se detectará hasta el tiempo de ejecución.  
  
 En las versiones 1.0 y 1.1 del lenguaje de C#, puede evitar los peligros del código generalizado en las clases de colección de la biblioteca de clases base de .NET Framework solo escribiendo sus propias colecciones específicas de tipo. Por supuesto, como dicha clase no es reutilizable para más de un tipo de datos, se pierden las ventajas de la generalización y tiene que volver a escribir la clase para cada tipo que se almacenará.  
  
 Lo que <xref:System.Collections.ArrayList> y otras clases similares realmente necesitan es una manera de que el código de cliente especifique, en una base por instancia, el tipo de datos determinado que pretenden usar. Eso eliminaría la necesidad de la conversión a <xref:System.Object> y también haría posible que el compilador realizara una comprobación de tipos. En otras palabras, <xref:System.Collections.ArrayList> necesita un parámetro de tipo. Eso es exactamente lo que proporcionan los genéricos. En la colección <xref:System.Collections.Generic.List%601> genérica, en el espacio de nombres <xref:System.Collections.Generic>, la misma operación de agregar elementos a la colección tiene este aspecto:  
  
 [!code-csharp[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]  
  
 Para el código de cliente, la única sintaxis agregada con <xref:System.Collections.Generic.List%601> en comparación con <xref:System.Collections.ArrayList> es el argumento de tipo en la declaración y creación de instancias. A cambio de esta complejidad de codificación ligeramente mayor, puede crear una lista que no solo es más segura que <xref:System.Collections.ArrayList>, sino también significativamente más rápida, especialmente cuando los elementos de lista son tipos de valor.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic>
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)
- [Conversión boxing y conversión unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
- [Cuándo utilizar colecciones genéricas](../../../standard/collections/when-to-use-generic-collections.md)
- [Instrucciones para colecciones](../../../standard/design-guidelines/guidelines-for-collections.md)
