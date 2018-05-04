---
title: Genéricos (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: 8f412366072c81b8aaca94829e0aa214f356200d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="generics-c-programming-guide"></a>Genéricos (Guía de programación de C#)
Los genéricos se han agregado a la versión 2.0 del lenguaje C# y Common Language Runtime (CLR). Los genéricos introducen en .NET Framework el concepto de parámetros de tipo, lo que le permite diseñar clases y métodos que aplazan la especificación de uno o varios tipos hasta que el código de cliente declare y cree una instancia de la clase o el método. Por ejemplo, al usar un parámetro de tipo genérico T puede escribir una clase única que otro código de cliente puede usar sin incurrir en el costo o riesgo de conversiones en tiempo de ejecución u operaciones de conversión boxing, como se muestra aquí:  
  
 [!code-csharp[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]  
  
## <a name="generics-overview"></a>Información general sobre los genéricos  
  
-   Use tipos genéricos para maximizar la reutilización del código, la seguridad de tipos y el rendimiento.  
  
-   El uso más común de los genéricos es crear clases de colección.  
  
-   La biblioteca de clases .NET Framework contiene varias clases de colección genéricas nuevas en el espacio de nombres <xref:System.Collections.Generic>. Estas se deberían usar siempre que sea posible en lugar de clases como <xref:System.Collections.ArrayList> en el espacio de nombres <xref:System.Collections>.  
  
-   Puede crear sus propias interfaces, clases, métodos, eventos y delegados genéricos.  
  
-   Puede limitar las clases genéricas para habilitar el acceso a métodos en tipos de datos determinados.  
  
-   Puede obtener información sobre los tipos que se usan en un tipo de datos genérico en tiempo de ejecución mediante la reflexión.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Para obtener más información:  
  
-   [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [Ventajas de los genéricos](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [Parámetros de tipo genérico](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [Clases genéricas](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [Interfaces genéricas](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [Métodos genéricos](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [Delegados genéricos](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [Diferencias entre plantillas de C++ y tipos genéricos de C#](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [Genéricos y reflexión](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [Genéricos en el motor en tiempo de ejecución](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 Para obtener más información, consulte la [Especificación del lenguaje C#](../../../csharp/language-reference/language-specification/index.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Generic>  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Tipos](../../../csharp/programming-guide/types/index.md)  
 [\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)  
 [\<typeparamref>](../../../csharp/programming-guide/xmldoc/typeparamref.md)  
 [Elementos genéricos en .NET](../../../standard/generics/index.md)  