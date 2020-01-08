---
title: 'Genéricos: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: 330aa74538ab15d1de19d80b0f57b3d0921c5c55
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712161"
---
# <a name="generics-c-programming-guide"></a>Genéricos (Guía de programación de C#)

Los genéricos introducen el concepto de parámetros de tipo a .NET Framework, lo que le permite diseñar clases y métodos que aplazan la especificación de uno o varios tipos hasta que el código de cliente declare y cree una instancia de la clase o el método. Por ejemplo, al usar un parámetro de tipo genérico `T`, puede escribir una clase única que otro código de cliente puede usar sin incurrir en el costo o riesgo de conversiones en tiempo de ejecución u operaciones de conversión boxing, como se muestra aquí:

[!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]

Las clases y métodos genéricos combinan reusabilidad, seguridad de tipos y eficacia de una manera en que sus homólogos no genéricos no pueden. Los genéricos se usan frecuentemente con colecciones y los métodos que funcionan en ellas. El espacio de nombres <xref:System.Collections.Generic> contiene varias clases de colecciones basadas en genéricos. No se recomiendan las colecciones no genéricas, como <xref:System.Collections.ArrayList>, y se mantienen por compatibilidad. Para más información, vea [Elementos genéricos en .NET](../../../standard/generics/index.md).

Por supuesto, también se pueden crear tipos y métodos genéricos personalizados para proporcionar soluciones y patrones de diseño generalizados propios con seguridad de tipos y eficaces. En el ejemplo de código siguiente se muestra una clase genérica simple de lista vinculada para fines de demostración. (En la mayoría de los casos, se debe usar la clase <xref:System.Collections.Generic.List%601> proporcionada por la biblioteca de clases .NET Framework en lugar de crear una propia). El parámetro de tipo `T` se usa en diversas ubicaciones donde normalmente se usaría un tipo concreto para indicar el tipo del elemento almacenado en la lista. Se usa de estas formas:

- Como el tipo de un parámetro de método en el método `AddHead`.
- Como el tipo de valor devuelto de la propiedad `Data` en la clase anidada `Node`.
- Como el tipo de miembro privado `data` de la clase anidada.

 Tenga en cuenta que `T` está disponible para la clase anidada `Node`. Cuando se crea una instancia de `GenericList<T>` con un tipo concreto, por ejemplo como un `GenericList<int>`, cada repetición de `T` se sustituye por `int`.

[!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)] 

En el ejemplo de código siguiente se muestra cómo el código de cliente usa la clase genérica `GenericList<T>` para crear una lista de enteros. Simplemente cambiando el argumento de tipo, el código siguiente puede modificarse fácilmente para crear listas de cadenas o cualquier otro tipo personalizado:

[!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]

## <a name="generics-overview"></a>Introducción a los genéricos

- Use tipos genéricos para maximizar la reutilización del código, la seguridad de tipos y el rendimiento.
- El uso más común de los genéricos es crear clases de colección.
- La biblioteca de clases .NET Framework contiene varias clases de colección genéricas nuevas en el espacio de nombres <xref:System.Collections.Generic>. Estas se deberían usar siempre que sea posible en lugar de clases como <xref:System.Collections.ArrayList> en el espacio de nombres <xref:System.Collections>.
- Puede crear sus propias interfaces, clases, métodos, eventos y delegados genéricos.
- Puede limitar las clases genéricas para habilitar el acceso a métodos en tipos de datos determinados.
- Puede obtener información sobre los tipos que se usan en un tipo de datos genérico en tiempo de ejecución mediante la reflexión.

## <a name="related-sections"></a>Secciones relacionadas

- [Parámetros de tipo genérico](generic-type-parameters.md)
- [Restricciones de tipos de parámetros](constraints-on-type-parameters.md)
- [Clases genéricas](generic-classes.md)
- [Interfaces genéricas](generic-interfaces.md)
- [Métodos genéricos](generic-methods.md)
- [Delegados genéricos](generic-delegates.md)
- [Diferencias entre plantillas de C++ y tipos genéricos de C#](differences-between-cpp-templates-and-csharp-generics.md)
- [Genéricos y reflexión](generics-and-reflection.md)
- [Genéricos en el motor en tiempo de ejecución](generics-in-the-run-time.md)

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, consulte la [Especificación del lenguaje C#](~/_csharplang/spec/types.md#constructed-types).

## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic>
- [Guía de programación de C#](../index.md)
- [Tipos](../types/index.md)
- [\<typeparam>](../xmldoc/typeparam.md)
- [\<typeparamref>](../xmldoc/typeparamref.md)
- [Elementos genéricos en .NET](../../../standard/generics/index.md)
