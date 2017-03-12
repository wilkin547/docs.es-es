---
title: "remove (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "remove_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "remove (descriptor de acceso de un evento) [C#]"
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
caps.latest.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 8
---
# remove (Referencia de C#)
La palabra clave contextual `remove` se utiliza para definir un descriptor de acceso de evento personalizado que se invoca cuando el código de cliente cancela la suscripción al [evento](../../../csharp/language-reference/keywords/event.md).  Si proporciona un descriptor de acceso `remove` personalizado, también debe proporcionar un descriptor de acceso [add](../../../csharp/language-reference/keywords/add.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra un evento con descriptores de acceso [add](../../../csharp/language-reference/keywords/add.md) y `remove` personalizados.  Para obtener el ejemplo completo, vea [Cómo: Implementar eventos de interfaz](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-cs[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/csharp/remove_1.cs)]  
  
 Por regla general, no necesita proporcionar sus propios descriptores de acceso de evento personalizados.  Los descriptores de acceso que genera automáticamente el compilador al declarar un evento son suficientes para la mayoría de los escenarios.  
  
## Vea también  
 [Eventos](../../../csharp/programming-guide/events/index.md)