---
title: "Operador - (Referencia de C#) | Microsoft Docs"
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
  - "-_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "- (operador) [C#]"
  - "- (operador de resta) [C#]"
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operador - (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El operador `-` puede funcionar como operador unario o binario.  
  
## Comentarios  
 Los operadores unarios `-` se encuentran predefinidos para todos los tipos numéricos.  El resultado de una operación unaria `-` aplicada a un tipo numérico es la negación numérica del operando.  
  
 Los operadores binarios `-` están predefinidos para todos los tipos numéricos y de enumeración de modo que restan el segundo operando del primero.  
  
 Los tipos delegados también proporcionan un operador binario `-`, el cual realiza la eliminación de delegados.  
  
 Los tipos definidos por el usuario pueden sobrecargar los operadores unario y binario `-`.  Para obtener más información, vea [operador](../../../csharp/language-reference/keywords/operator.md).  
  
## Ejemplo  
 [!code-cs[csRefOperators#40](../../../csharp/language-reference/operators/codesnippet/CSharp/subtraction-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)