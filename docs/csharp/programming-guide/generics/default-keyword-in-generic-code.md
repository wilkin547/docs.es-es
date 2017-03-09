---
title: "Palabra clave predeterminada en c&#243;digo gen&#233;rico (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "default (palabra clave) [C#], programación genérica"
  - "genéricos [C#], default (palabra clave)"
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# Palabra clave predeterminada en c&#243;digo gen&#233;rico (Gu&#237;a de programaci&#243;n de C#)
Un problema asociado a las clases y métodos genéricos es la forma de asignar un valor predeterminado a un tipo parametrizado T cuando no se tiene por anticipado la siguiente información:  
  
-   Si T será un tipo de referencia o un tipo de valor.  
  
-   Si T es un tipo de valor, si será un valor numérico o un struct.  
  
 Dada una variable t de un tipo parametrizado T, la instrucción t \= null sólo es válida si T es un tipo de referencia y t \= 0 sólo funcionará con los tipos de valor numérico, pero no con los structs.  La solución es utilizar la palabra clave `default`, que devolverá null para los tipos de referencia y cero para los tipos de valor numérico.  En el caso de los structs, devolverá cada miembro del struct inicializado con el valor cero o null, dependiendo de si son tipos de valor o de referencia.  Para los tipos de valor que aceptan valores NULL, default devuelve <xref:System.Nullable%601?displayProperty=fullName>, que se inicializa como cualquier struct.  
  
 El ejemplo siguiente de las clases `GenericList<T>` muestra cómo utilizar la palabra clave `default`.  Para obtener más información, vea [Información general sobre los genéricos \(Guía de programación de C\#\)](../../../csharp/programming-guide/generics/introduction-to-generics.md).  
  
 [!code-cs[csProgGuideGenerics#41](../../../csharp/programming-guide/generics/codesnippet/csharp/default-keyword-in-gener_1.cs)]  
  
## Vea también  
 <xref:System.Collections.Generic>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Genéricos](../../../csharp/programming-guide/generics/index.md)   
 [Métodos genéricos](../../../csharp/programming-guide/generics/generic-methods.md)   
 [Genéricos](../Topic/Generics%20in%20the%20.NET%20Framework.md)