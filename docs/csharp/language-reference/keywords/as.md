---
title: "as (Referencia de C#) | Microsoft Docs"
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
  - "as_CSharpKeyword"
  - "as"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "as (palabra clave) [C#]"
  - "conversión de tipos [C#], as (palabra clave)"
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# as (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Puede utilizar el operador de `as` para realizar algunos tipos de conversiones entre los tipos de referencia compatibles o [tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md).  El siguiente fragmento de código muestra un ejemplo.  
  
 [!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]  
  
## Comentarios  
 El operador `as` es como una operación de conversión de tipos.  Sin embargo, si la conversión no es posible, `as` devuelve `null` en lugar de producir una excepción.  Considere el ejemplo siguiente:  
  
```  
expression as type  
```  
  
 El código es equivalente a la siguiente expresión salvo que la variable de `expression` se evalúan sólo una vez.  
  
```  
expression is type ? (type)expression : (type)null  
```  
  
 Observe que el operador de `as` realiza sólo conversiones de referencia, conversiones que acepta valores NULL, y conversiones boxing.  El operador de `as` no puede realizar otras conversiones, como conversiones definidas por el usuario, que deben en su lugar realizar mediante expresiones de conversión.  
  
## Ejemplo  
 [!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [?: \(Operador\)](../../../csharp/language-reference/operators/conditional-operator.md)   
 [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)