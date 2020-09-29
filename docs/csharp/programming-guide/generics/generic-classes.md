---
title: 'Clases genéricas: Guía de programación de C#'
description: Aprenda sobre las clases genéricas utilizadas en colecciones como listas vinculadas, tablas hash, pilas, colas y árboles.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic classes
- generics [C#], classes
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
ms.openlocfilehash: 62e6e7afe0e795819b82c6c7a4f99260a8080efb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157426"
---
# <a name="generic-classes-c-programming-guide"></a>Clases genéricas (Guía de programación de C#)

Las clases genéricas encapsulan operaciones que no son específicas de un tipo de datos determinado. El uso más común de las clases genéricas es con colecciones como listas vinculadas, tablas hash, pilas, colas y árboles, entre otros. Las operaciones como la adición y eliminación de elementos de la colección se realizan básicamente de la misma manera independientemente del tipo de datos que se almacenan.  
  
 Para la mayoría de los escenarios que necesitan clases de colección, el enfoque recomendado es usar las que se proporcionan en la biblioteca de clases .NET. Para más información sobre el uso de estas clases, vea [Colecciones genéricas en .NET](../../../standard/generics/collections.md).  
  
 Normalmente, crea clases genéricas empezando con una clase concreta existente, y cambiando tipos en parámetros de tipo de uno en uno hasta que alcanza el equilibrio óptimo de generalización y facilidad de uso. Al crear sus propias clases genéricas, entre las consideraciones importantes se incluyen las siguientes:  
  
- Los tipos que se van a generalizar en parámetros de tipo.  
  
     Como norma, cuantos más tipos pueda parametrizar, más flexible y reutilizable será su código. En cambio, demasiada generalización puede crear código que sea difícil de leer o entender para otros desarrolladores.  
  
- Las restricciones, si existen, que se van a aplicar a los parámetros de tipo (Vea [Restricciones de parámetros de tipo](./constraints-on-type-parameters.md)).  
  
     Una buena norma es aplicar el máximo número de restricciones posible que todavía le permitan tratar los tipos que debe controlar. Por ejemplo, si sabe que su clase genérica está diseñada para usarse solo con tipos de referencia, aplique la restricción de clase. Esto evitará el uso no previsto de su clase con tipos de valor, y le permitirá usar el operador `as` en `T`, y comprobar si hay valores NULL.  
  
- Si separar el comportamiento genérico en clases base y subclases.  
  
     Como las clases genéricas pueden servir como clases base, las mismas consideraciones de diseño se aplican aquí con clases no genéricas. Vea las reglas sobre cómo heredar de clases base genéricas posteriormente en este tema.  
  
- Si implementar una o más interfaces genéricas.  
  
     Por ejemplo, si está diseñando una clase que se usará para crear elementos en una colección basada en genéricos, puede que tenga que implementar una interfaz como <xref:System.IComparable%601> donde `T` es el tipo de su clase.  
  
 Para obtener un ejemplo de una clase genérica simple, vea [Introducción a los genéricos](./index.md).  
  
 Las reglas para los parámetros de tipo y las restricciones tienen varias implicaciones para el comportamiento de clase genérico, especialmente respecto a la herencia y a la accesibilidad de miembros. Antes de continuar, debe entender algunos términos. Para una clase genérica `Node<T>,`, el código de cliente puede hacer referencia a la clase especificando un argumento de tipo, para crear un tipo construido cerrado (`Node<int>`). De manera alternativa, puede dejar el parámetro de tipo sin especificar, por ejemplo cuando especifica una clase base genérica, para crear un tipo construido abierto (`Node<T>`). Las clases genéricas pueden heredar de determinadas clases base construidas abiertas o construidas cerradas:  
  
 [!code-csharp[csProgGuideGenerics#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#16)]  
  
 Las clases no genéricas, en otras palabras, concretas, pueden heredar de clases base construidas cerradas, pero no desde clases construidas abiertas ni desde parámetros de tipo porque no hay ninguna manera en tiempo de ejecución para que el código de cliente proporcione el argumento de tipo necesario para crear instancias de la clase base.  
  
 [!code-csharp[csProgGuideGenerics#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#17)]  
  
 Las clases genéricas que heredan de tipos construidos abiertos deben proporcionar argumentos de tipo para cualquier parámetro de tipo de clase base que no se comparta mediante la clase heredada, como se demuestra en el código siguiente:  
  
 [!code-csharp[csProgGuideGenerics#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#18)]  
  
 Las clases genéricas que heredan de tipos construidos abiertos deben especificar restricciones que son un superconjunto de las restricciones del tipo base, o que las implican:  
  
 [!code-csharp[csProgGuideGenerics#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#19)]  
  
 Los tipos genéricos pueden usar varios parámetros de tipo y restricciones, de la manera siguiente:  
  
 [!code-csharp[csProgGuideGenerics#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#20)]  
  
 Tipos construidos cerrados y construidos abiertos pueden usarse como parámetros de método:  
  
 [!code-csharp[csProgGuideGenerics#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#21)]  
  
 Si una clase genérica implementa una interfaz, todas las instancias de esa clase se pueden convertir en esa interfaz.  
  
 Las clases genéricas son invariables. En otras palabras, si un parámetro de entrada especifica un `List<BaseClass>`, obtendrá un error en tiempo de compilación si intenta proporcionar un `List<DerivedClass>`.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Collections.Generic>
- [Guía de programación de C#](../index.md)
- [Genéricos](./index.md)
- [Guardar el estado de los enumeradores](/archive/blogs/wesdyer/saving-the-state-of-enumerators)
- [Un puzle de herencia, parte uno](/archive/blogs/ericlippert/an-inheritance-puzzle-part-one)
