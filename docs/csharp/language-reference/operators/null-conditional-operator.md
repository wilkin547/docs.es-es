---
title: "Operador ?? (Referencia de C#) | Microsoft Docs"
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
  - "??_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "?? (operador) [C#]"
  - "coalesce (operador) [C#]"
  - "&& (operador AND condicional) [C#]"
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operador ?? (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Al operador `??` se le llama el operador de uso combinado de NULL.  Dicho operador devuelve el operando izquierdo si no es NULL; de lo contrario, devuelve el operando derecho.  
  
## Comentarios  
 Un tipo que acepta valores NULL puede representar un valor del dominio del tipo, o el valor puede no estar definido \(en cuyo caso el valor es NULL\).  Se puede usar la expresividad sintáctica del operador `??` para devolver un valor apropiado \(el operando derecho\) cuando el operando izquierdo tenga un tipo que acepta valores NULL cuyo valor sea NULL.  Si se intenta asignar un tipo de valor que acepta valores NULL a otro que no sin usar el operador `??`, se generará un error en tiempo de compilación.  Si se usa una conversión y el tipo de valor que acepta valores NULL no está definido actualmente, se producirá una excepción `InvalidOperationException`.  
  
 Para obtener más información, vea [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md).  
  
 El resultado de un operador ?? no se considera una constante, incluso aunque sus dos argumentos sean constantes.  
  
## Ejemplo  
 [!code-cs[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)   
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [¿Qué significa exactamente "elevado"?](http://go.microsoft.com/fwlink/?LinkID=112382)