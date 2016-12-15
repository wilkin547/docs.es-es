---
title: "add (Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "add_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "add (descriptor de acceso de un evento) [C#]"
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# add (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La palabra clave contextual `add` se utiliza para definir un descriptor de acceso de evento personalizado que se invoca cuando el código de cliente se suscribe al [evento](../../../csharp/language-reference/keywords/event.md).  Si proporciona un descriptor de acceso `add` personalizado, también debe proporcionar un descriptor de acceso [remove](../../../csharp/language-reference/keywords/remove.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra un evento con descriptores de acceso `add` y [remove](../../../csharp/language-reference/keywords/remove.md) personalizados.  Para obtener el ejemplo completo, vea [Cómo: Implementar eventos de interfaz](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-cs[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/add_1.cs)]  
  
 Por regla general, no necesita proporcionar sus propios descriptores de acceso de evento personalizados.  Los descriptores de acceso que genera automáticamente el compilador al declarar un evento son suficientes para la mayoría de los escenarios.  
  
## Vea también  
 [Eventos](../../../csharp/programming-guide/events/index.md)