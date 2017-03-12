---
title: "Delegados gen&#233;ricos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "delegados [C#], genéricos"
  - "genéricos [C#], delegados"
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Delegados gen&#233;ricos (Gu&#237;a de programaci&#243;n de C#)
Un [delegado](../../../csharp/language-reference/keywords/delegate.md) puede definir sus propios parámetros de tipo.  El código que hace referencia al delegado genérico puede especificar el tipo de argumento para crear un tipo construido abierto, igual que al crear una instancia de una clase genérica o al llamar a un método genérico, como se muestra en el siguiente ejemplo:  
  
 [!code-cs[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-delegates_1.cs)]  
  
 C\# 2.0 tiene una nueva característica denominada conversión de grupo de métodos, que se aplica a los tipos delegados concretos y genéricos, y permite escribir la línea anterior con esta sintaxis simplificada:  
  
 [!code-cs[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-delegates_2.cs)]  
  
 Los delegados definidos dentro de una clase genérica pueden utilizar los parámetros de tipo de la clase genérica de la misma manera que lo hacen los métodos de clase.  
  
 [!code-cs[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-delegates_3.cs)]  
  
 El código que hace referencia al delegado debe especificar el argumento de tipo de la clase contenedora, de la siguiente manera:  
  
 [!code-cs[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-delegates_4.cs)]  
  
 Los delegados genéricos son especialmente útiles para definir eventos basados en el patrón de diseño habitual porque el argumento del remitente puede estar fuertemente tipado y ya no tiene que convertirse a y de <xref:System.Object>.  
  
 [!code-cs[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-delegates_5.cs)]  
  
## Vea también  
 <xref:System.Collections.Generic>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Métodos genéricos](../../../csharp/programming-guide/generics/generic-methods.md)   
 [Clases genéricas](../../../csharp/programming-guide/generics/generic-classes.md)   
 [Interfaces genéricas](../../../csharp/programming-guide/generics/generic-interfaces.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)   
 [Genéricos](../Topic/Generics%20in%20the%20.NET%20Framework.md)