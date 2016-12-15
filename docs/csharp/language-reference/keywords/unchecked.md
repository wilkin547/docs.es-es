---
title: "unchecked (Referencia de C#) | Microsoft Docs"
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
  - "unchecked_CSharpKeyword"
  - "unchecked"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "unchecked (palabra clave) [C#]"
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# unchecked (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La palabra clave `unchecked` se utiliza con el fin de suprimir la comprobación de desbordamiento para operaciones aritméticas y conversiones de tipo integral.  
  
 En un contexto sin comprobación de desbordamiento, si una expresión genera un valor fuera del intervalo del tipo de destino, no se marca el desbordamiento.  Por ejemplo, como el cálculo en el siguiente ejemplo se realiza en una expresión o un bloque `unchecked`, se pasa por alto que el resultado es demasiado grande para un valor entero y se asigna a `int1` el valor \-2.147.483.639.  
  
 [!code-cs[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]  
  
 Si se quita el entorno `unchecked`, se produce un error de compilación.  Se puede detectar el desbordamiento en tiempo de compilación porque todos los términos de la expresión son constantes.  
  
 De forma predeterminada, se suprime la comprobación de desbordamiento de las expresiones que contienen términos no constantes en tiempo de compilación y tiempo de ejecución.  Vea [checked](../../../csharp/language-reference/keywords/checked.md) para obtener información sobre un entorno con comprobación de desbordamiento.  
  
 Dado que la comprobación de desbordamiento requiere tiempo, el uso de código sin comprobación podría mejorar el rendimiento en casos en los que no existe riesgo de desbordamiento.  Sin embargo, si existe la posibilidad de que se produzca un desbordamiento, se debe usar un entorno con comprobación de desbordamiento.  
  
## Ejemplo  
 En este ejemplo, se muestra cómo usar la palabra clave `unchecked`.  
  
 [!code-cs[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Checked y unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)   
 [checked](../../../csharp/language-reference/keywords/checked.md)