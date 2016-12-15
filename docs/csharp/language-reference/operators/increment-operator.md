---
title: "Operador ++ (Referencia de C#) | Microsoft Docs"
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
  - "++_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "++ (operador) [C#]"
  - "operador de incremento (++) [C#]"
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operador ++ (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El operador de incremento \(`++`\) incrementa su operando en 1. El operador de incremento puede aparecer antes o después de su operando: `++variable` y `variable++`.  
  
## Comentarios  
 La primera forma es una operación de incremento de prefijo. El resultado de la operación es el valor del operando después del incremento.  
  
 La segunda forma es una operación de incremento de postfijo. El resultado de la operación es el valor del operando antes del incremento.  
  
 Los tipos numéricos y de enumeración poseen operadores de incremento predefinidos. Los tipos definidos por el usuario pueden sobrecargar el operador `++`. Las operaciones de tipos enteros suelen estar permitidas en la enumeración.  
  
## Ejemplo  
 [!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)