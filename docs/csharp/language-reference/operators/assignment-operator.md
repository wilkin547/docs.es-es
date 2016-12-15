---
title: "Operador = (Referencia de C#) | Microsoft Docs"
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
  - "=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "= (operador) [C#]"
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operador = (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El operador de asignación \(`=`\) almacena el valor del operando situado a su derecha en la ubicación de almacenamiento, propiedad o indizador indicados por el operando situado a su izquierda y devuelve el valor como resultado.  Los operandos deben ser del mismo tipo \(o el operando de la derecha se debe poder convertir implícitamente al tipo del operando de la izquierda\).  
  
## Comentarios  
 El operador de asignación no se puede sobrecargar.  Sin embargo, se pueden definir operadores de conversión implícita para un tipo, los cuales permiten usar el operador de asignación con esos tipos.  Para obtener más información, vea [Utilizar operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## Ejemplo  
 [!code-cs[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)