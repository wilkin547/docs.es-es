---
title: "object (Referencia de C#) | Microsoft Docs"
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
  - "object_CSharpKeyword"
  - "object"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "object (palabra clave) [C#]"
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# object (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El tipo `object` es un alias de <xref:System.Object> en .NET Framework.  En el sistema de tipos unificado de C\#, todos los tipos \(tipos de valor y de referencia predefinidos y definidos por el usuario\) se heredan directa o indirectamente de <xref:System.Object>.  Las variables de tipo `object` pueden recibir valores de cualquier tipo.  Cuando una variable de un tipo de valor se convierte en un objeto, se dice que se le ha aplicado la *conversión boxing*.  Cuando una variable de objeto de tipo se convierte en un tipo de valor, se dice que se le ha aplicado la *conversión unboxing*.  Para obtener más información, vea [Boxing y Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).  
  
## Ejemplo  
 En el siguiente ejemplo se muestra cómo las variables de tipo `object` pueden aceptar valores de cualquier tipo de datos y cómo pueden utilizar métodos de <xref:System.Object> procedentes de .NET Framework.  
  
 [!code-cs[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md)   
 [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md)