---
title: "Pasar par&#225;metros (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "argumentos [C#]"
  - "lenguaje C#, parámetros de métodos"
  - "métodos [C#], pasar parámetros"
  - "parámetros [C#], pasar"
  - "pasar parámetros [C#]"
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Pasar par&#225;metros (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En C\#, los argumentos se pueden pasar a parámetros por valor o por referencia.  El paso de parámetros por referencia permite a los miembros de funciones, métodos, propiedades, indizadores, operadores y constructores cambiar el valor de los parámetros y hacer que ese cambio persista en el entorno que procede de la llamada.  Para pasar un parámetro por referencia, utilice una de las palabras clave `ref` o `out`.  En los ejemplos de este tema, para simplificar, sólo se utiliza la palabra clave `ref`.  Para obtener más información sobre la diferencia entre `ref` y `out`, vea [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md) y [Pasar matrices mediante Ref y Out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 En el ejemplo siguiente se muestra la diferencia entre valor y parámetros de referencia.  
  
 [!code-cs[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 Para obtener más información, vea los temas siguientes:  
  
-   [Pasar parámetros de tipo de valor](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [Pasar parámetros Reference\-Type](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)