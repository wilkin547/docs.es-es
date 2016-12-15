---
title: "Tipos anidados (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "tipos anidados [C#]"
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Tipos anidados (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Un tipo definido en una [clase](../../../csharp/language-reference/keywords/class.md) o [struct](../../../csharp/language-reference/keywords/struct.md) se denomina tipo anidado.  Por ejemplo:  
  
 [!code-cs[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
 Con independencia de si el tipo externo es una clase o struct, los tipos anidados se establecen de forma predeterminada en [private](../../../csharp/language-reference/keywords/private.md), pero pueden definirse como [public](../../../csharp/language-reference/keywords/public.md), protected internal, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md).  En el ejemplo anterior, `Nested` es inaccesible a los tipos externos, pero se puede establecer en public de la manera siguiente:  
  
 [!code-cs[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 El tipo anidado o interno puede tener acceso al tipo contenedor o externo.  Para tener acceso al tipo contenedor, páselo como constructor al tipo anidado.  Por ejemplo:  
  
 [!code-cs[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 Un tipo anidado tiene acceso a todos los miembros que estén accesibles para el tipo contenedor.  Puede tener acceso a los miembros privados y protegidos del tipo contenedor, incluidos los miembros protegidos heredados.  
  
 En la declaración anterior, el nombre completo de la clase `Nested` es `Container.Nested`.  Este es el nombre que se utiliza para crear una instancia nueva de la clase anidada, de la siguiente manera:  
  
 [!code-cs[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)