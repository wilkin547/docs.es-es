---
title: "checked (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "checked_CSharpKeyword"
  - "checked"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "checked (palabra clave) [C#]"
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# checked (Referencia de C#)
La palabra clave `checked` se usa con el fin de habilitar explícitamente la comprobación de desbordamiento para operaciones aritméticas y conversiones de tipo integral.  
  
 De forma predeterminada, una expresión que solo contiene valores constantes da lugar a un error del compilador si genera un valor fuera del intervalo del tipo de destino.  Si la expresión contiene uno o varios valores no constantes, el compilador no detecta el desbordamiento.  En el siguiente ejemplo, la evaluación de la expresión asignada a `i2` no genera un error del compilador.  
  
 [!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/csharp/checked_1.cs)]  
  
 De forma predeterminada, estas expresiones no constantes no se someten a la comprobación de desbordamiento en tiempo de ejecución y no generan excepciones de desbordamiento.  En el ejemplo anterior, se muestra \-2.147.483.639 como la suma de dos enteros positivos.  
  
 La comprobación de desbordamiento se puede habilitar mediante opciones del compilador, la configuración del entorno o la palabra clave `checked`.  En los ejemplos siguientes, se muestra cómo usar una expresión `checked` o un bloque `checked` para detectar el desbordamiento generado por la suma anterior en tiempo de ejecución.  En ambos ejemplos se genera una excepción de desbordamiento.  
  
 [!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/csharp/checked_2.cs)]  
  
 Se puede usar la palabra clave [unchecked](../../../csharp/language-reference/keywords/unchecked.md) para evitar la comprobación de desbordamiento.  
  
## Ejemplo  
 En este ejemplo, se muestra cómo usar `checked` para habilitar la comprobación de desbordamiento en tiempo de ejecución.  
  
 [!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/csharp/checked_3.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Checked y unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)   
 [unchecked](../../../csharp/language-reference/keywords/unchecked.md)