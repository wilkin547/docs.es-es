---
title: "Gen&#233;ricos y atributos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "atributos [C#], con genéricos"
  - "genéricos [C#], atributos"
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# Gen&#233;ricos y atributos (Gu&#237;a de programaci&#243;n de C#)
Los atributos se pueden aplicar a los tipos genéricos de la misma manera que a los tipos no genéricos.  Para obtener más información sobre la aplicación de atributos, vea [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Los atributos personalizados sólo pueden hacer referencia a tipos genéricos abiertos, es decir, tipos genéricos en los que no se indican argumentos de tipo, y tipos genéricos construidos cerrados, que proporcionan argumentos para todos los parámetros del tipo.  
  
 En los ejemplos siguientes se utiliza este atributo personalizado:  
  
 [!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-attributes_1.cs)]  
  
 Un atributo puede hacer referencia a un tipo genérico abierto:  
  
 [!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-attributes_2.cs)]  
  
 Especifique varios parámetros de tipo mediante el número adecuado de comas.  En este ejemplo, `GenericClass2` tiene dos parámetros de tipo:  
  
 [!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-attributes_3.cs)]  
  
 Un atributo puede hacer referencia a un tipo genérico construido cerrado:  
  
 [!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-attributes_4.cs)]  
  
 Un atributo que hace referencia a un parámetro de tipo genérico producirá un error de compilación:  
  
 [!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-attributes_5.cs)]  
  
 Un tipo genérico no puede heredar de <xref:System.Attribute>:  
  
 [!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-attributes_6.cs)]  
  
 Para obtener información sobre un tipo genérico o parámetro de tipo en tiempo de ejecución, puede utilizar los métodos de <xref:System.Reflection>.  Para obtener más información, vea [Genéricos y reflexión](../../../csharp/programming-guide/generics/generics-and-reflection.md).  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Genéricos](../../../csharp/programming-guide/generics/index.md)   
 [Atributos](../Topic/Extending%20Metadata%20Using%20Attributes.md)