---
title: "Utilizar operadores de conversi&#243;n (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "operadores de conversión [C#]"
  - "conversiones [C#], operadores"
  - "operadores de conversión explícita [C#]"
  - "operadores de conversión implícita [C#]"
  - "operadores [C#], conversión"
  - "conversiones definidas por el usuario [C#]"
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Utilizar operadores de conversi&#243;n (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Puede usar los operadores de conversión `implicit`, que son más fáciles de usar, o los operadores de conversión `explicit`, que indican claramente a cualquiera que lea el código que está convirtiendo un tipo.  En este tema se muestran ambos tipos de operadores de conversión.  
  
> [!NOTE]
>  Para obtener más información sobre las conversiones de tipos simples, vea [Cómo: Convertir una cadena en un número](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [Cómo: Convertir una matriz de bytes en un valor int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Cómo: Convertir cadenas hexadecimales en tipos numéricos](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) o <xref:System.Convert>.  
  
## Ejemplo  
 Este es un ejemplo de un operador de conversión explícita.  Este operador convierte el tipo <xref:System.Byte> en un tipo de valor denominado `Digit`.  Como no todos los bytes se pueden convertir en valores de tipo digit, la conversión es explícita, lo que significa que se debe usar una conversión, como se muestra en el método `Main`.  
  
 [!code-cs[csProgGuideStatements#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_1.cs)]  
  
## Ejemplo  
 En este ejemplo se muestra un operador de conversión implícita mediante la definición de un operador de conversión que deshace lo que hizo el ejemplo anterior: convierte una clase de valor denominada `Digit` en el tipo entero <xref:System.Byte>.  Dado que cualquier dígito se puede convertir en <xref:System.Byte>, no hay ninguna necesidad de obligar a los usuarios a que definan explícitamente la conversión.  
  
 [!code-cs[csProgGuideStatements#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_2.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)   
 [is](../../../csharp/language-reference/keywords/is.md)