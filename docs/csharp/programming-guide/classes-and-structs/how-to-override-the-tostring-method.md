---
title: "C&#243;mo: Invalidar el m&#233;todo ToString (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "herencia [C#], invalidar OnPaint y ToString"
  - "ToString (método), invalidar en C#"
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Invalidar el m&#233;todo ToString (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Cada clase o struct de C\# hereda implícitamente la clase <xref:System.Object>.  Por consiguiente, cada objeto de C\# obtiene el método <xref:System.Object.ToString%2A>, que devuelve una representación de cadena de ese objeto.  Por ejemplo, todas las variables de tipo `int` tienen un método `ToString`, que las habilita para devolver su contenido como cadena:  
  
 [!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]  
  
 Cuando cree una clase o struct personalizados, debe reemplazar el método <xref:System.Object.ToString%2A> para proporcionar información sobre el tipo al código de cliente.  
  
 Para obtener información sobre cómo usar cadenas de formato y otros tipos de formato personalizado con el método de `ToString` , vea [Aplicar formato a tipos](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md).  
  
> [!IMPORTANT]
>  Cuando decida qué información va a proporcionar a través de este método, considere si la clase o struct se va a utilizar alguna vez en código que no sea de confianza.  Asegúrese de que no proporciona información que pueda ser aprovechada por código malintencionado.  
  
### Para reemplazar el método ToString en una clase o struct  
  
1.  Declare un método `ToString` con los modificadores y tipo de valor devuelto siguientes:  
  
    ```c#  
    public override string ToString(){}  
    ```  
  
2.  Implemente el método para que devuelva una cadena.  
  
     En el ejemplo siguiente, se devuelve el nombre de la clase, además de los datos específicos de una instancia concreta de la clase.  
  
     [!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]  
  
     Se puede probar el método `ToString` tal y como se muestra en el siguiente ejemplo de código:  
  
     [!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]  
  
## Vea también  
 <xref:System.IFormattable>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Cadenas](../../../csharp/programming-guide/strings/index.md)   
 [string](../../../csharp/language-reference/keywords/string.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)   
 [Aplicar formato a tipos](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md)