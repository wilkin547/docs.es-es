---
title: "Genéricos y atributos (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5136ae928a3a4b6f8ec4d86100d695f958d55858
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-attributes-c-programming-guide"></a>Genéricos y atributos (Guía de programación de C#)
Los atributos pueden aplicarse a los tipos genéricos de la misma manera que los tipos no genéricos. Para obtener más información sobre la aplicación de los atributos, vea [Atributos](../../../csharp/programming-guide/concepts/attributes/index.md).  
  
 Los atributos personalizados solo se permiten para hacer referencia a tipos genéricos abiertos, que son tipos genéricos para los que no se proporciona ningún argumento de tipo, y tipos genéricos construidos cerrados, que proporcionan argumentos para todos los parámetros de tipo.  
  
 En los ejemplos siguientes se usa este atributo personalizado:  
  
 [!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]  
  
 Un atributo puede hacer referencia a un tipo genérico abierto:  
  
 [!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]  
  
 Especifica varios parámetros de tipo con el número de comas apropiado. En este ejemplo, `GenericClass2` tiene dos parámetros de tipo:  
  
 [!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]  
  
 Un atributo puede hacer referencia a un tipo genérico construido cerrado:  
  
 [!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]  
  
 Un atributo que hace referencia a un parámetro de tipo genérico provocará un error en tiempo de compilación:  
  
 [!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]  
  
 Un tipo genérico no puede heredarse de <xref:System.Attribute>:  
  
 [!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]  
  
 Para obtener información sobre un tipo genérico o un parámetro de tipo en tiempo de ejecución, puede usar los métodos de <xref:System.Reflection>. Para obtener más información, vea [Genéricos y reflexión](../../../csharp/programming-guide/generics/generics-and-reflection.md).  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Genéricos](../../../csharp/programming-guide/generics/index.md)   
 [Atributos](https://msdn.microsoft.com/library/5x6cd29c)

