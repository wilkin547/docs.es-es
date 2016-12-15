---
title: "C&#243;mo: Realizar conversiones seguras usando los operadores is y as (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "as (operador) [C#]"
  - "operadores de conversión [C#], as e is (operadores)"
  - "is (operador) [C#]"
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Realizar conversiones seguras usando los operadores is y as (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Dado que los objetos son polimórficos, es posible que una variable de un tipo de clase base contenga un tipo derivado.  Para tener acceso al método del tipo derivado, es necesario volver a convertir el valor al tipo derivado.  Sin embargo, el intento de realizar una conversión de tipos sencilla en estos casos conlleva el riesgo de producir una excepción <xref:System.InvalidCastException>.  Por esa razón, C\# proporciona los operadores [is](../../../csharp/language-reference/keywords/is.md) y [as](../../../csharp/language-reference/keywords/as.md).  Puede utilizar estos operadores para comprobar si una conversión de tipo se realizará correctamente sin hacer que se produzca una excepción.  En general, el operador `as` suele ser más eficaz, ya que devuelve el valor de la conversión de tipo si esta puede realizarse correctamente.  El operador `is` devuelve solamente un valor Boolean.  Así, puede utilizarse cuando simplemente desee determinar el tipo de un objeto pero no tenga que realizar una conversión de tipo del mismo.  
  
## Ejemplo  
 En los ejemplos siguientes se muestra cómo utilizar los operadores `is` y `as` para realizar una conversión de un tipo de referencia a otro sin el riesgo de que se produzca una excepción.  En el ejemplo también se muestra cómo utilizar el operador `as` con tipos de valor que aceptan valores NULL.  
  
 [!code-cs[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]  
  
## Vea también  
 [Tipos](../../../csharp/programming-guide/types/index.md)   
 [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)