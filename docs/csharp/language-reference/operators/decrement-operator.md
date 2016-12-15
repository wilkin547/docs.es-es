---
title: "Operador -- (Referencia de C#) | Microsoft Docs"
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
  - "--_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-- (operador) [C#]"
  - "operador de decremento (--) [C#]"
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operador -- (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El operador de decremento \(`--`\) decrementa su operando en 1.  El operador de decremento puede aparecer antes o después de su operando: `--variable` y `variable--`.  La primera forma es una operación de decremento prefijo.  El resultado de la operación es el valor del operando "después" de haber sido decrementado.  La segunda forma es una operación de decremento postfijo.  El resultado de la operación es el valor del operando "antes" de haber sido decrementado.  
  
## Comentarios  
 Los tipos numéricos y de enumeración poseen operadores de decremento predefinidos.  
  
 Los tipos definidos por el usuario pueden sobrecargar el operador `--` \(vea [operador](../../../csharp/language-reference/keywords/operator.md)\).  Las operaciones en tipos enteros se suelen permitir en enumeraciones.  
  
## Ejemplo  
 [!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)