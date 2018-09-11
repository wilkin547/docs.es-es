---
title: Genéricos y atributos (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 0fe2d61001584aa7c175500bfa754b2ae2244660
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44209256"
---
# <a name="generics-and-attributes-c-programming-guide"></a>Genéricos y atributos (Guía de programación de C#)
Los atributos pueden aplicarse a los tipos genéricos de la misma manera que los tipos no genéricos. Para obtener más información sobre la aplicación de los atributos, vea [Atributos](../../../csharp/programming-guide/concepts/attributes/index.md).  
  
 Los atributos personalizados solo se permiten para hacer referencia a tipos genéricos abiertos, que son tipos genéricos para los que no se proporciona ningún argumento de tipo, y tipos genéricos construidos cerrados, que proporcionan argumentos para todos los parámetros de tipo.  
  
 En los ejemplos siguientes se usa este atributo personalizado:  
  
 [!code-csharp[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]  
  
 Un atributo puede hacer referencia a un tipo genérico abierto:  
  
 [!code-csharp[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]  
  
 Especifica varios parámetros de tipo con el número de comas apropiado. En este ejemplo, `GenericClass2` tiene dos parámetros de tipo:  
  
 [!code-csharp[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]  
  
 Un atributo puede hacer referencia a un tipo genérico construido cerrado:  
  
 [!code-csharp[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]  
  
 Un atributo que hace referencia a un parámetro de tipo genérico provocará un error en tiempo de compilación:  
  
 [!code-csharp[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]  
  
 Un tipo genérico no puede heredarse de <xref:System.Attribute>:  
  
 [!code-csharp[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]  
  
 Para obtener información sobre un tipo genérico o un parámetro de tipo en tiempo de ejecución, puede usar los métodos de <xref:System.Reflection>. Para obtener más información, vea [Genéricos y reflexión](../../../csharp/programming-guide/generics/generics-and-reflection.md).  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Genéricos](../../../csharp/programming-guide/generics/index.md)  
- [Atributos](../../../../docs/standard/attributes/index.md)
