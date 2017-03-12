---
title: "explicit (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "explicit_CSharpKeyword"
  - "explicit"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "explicit (palabra clave) [C#]"
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# explicit (Referencia de C#)
La palabra clave `explicit` declara un operador de conversión de tipos definido por el usuario que se debe invocar con una conversión de tipos.  Por ejemplo, este operador convierte una clase denominada Fahrenheit en una clase denominada Celsius:  
  
 [!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/csharp/explicit_1.cs)]  
  
 El operador de conversión se puede invocar así:  
  
 [!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/csharp/explicit_2.cs)]  
  
 El operador de conversión convierte un tipo de origen en un tipo de destino.  El tipo de origen proporciona el operador de conversión.  A diferencia de la conversión implícita, los operadores de conversión explícita deben invocarse mediante una conversión de tipo \(cast\).  Si una operación de conversión puede producir excepciones o pérdida de información, debe marcarse como `explicit`.  De esta forma, se evita que el compilador realice la conversión automáticamente y se produzcan posibles consecuencias no deseadas.  
  
 Omitir los resultados de conversión del error en tiempo de compilación CS0266.  
  
 Para obtener más información, vea [Utilizar operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## Ejemplo  
 El ejemplo siguiente proporciona una clase `Fahrenheit` y una clase `Celsius`, cada una de las cuales proporciona un operador de conversión explícito a la otra clase.  
  
 [!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/csharp/explicit_3.cs)]  
  
## Ejemplo  
 El siguiente ejemplo define un struct, `Digit`, que representa un único dígito decimal.  Se define un operador para conversiones de `byte` a `Digit`, pero como no todos los bytes se pueden convertir en `Digit`, la conversión es explícita.  
  
 [!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/csharp/explicit_4.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [implícita](../../../csharp/language-reference/keywords/implicit.md)   
 [operador](../../../csharp/language-reference/keywords/operator.md)   
 [Cómo: Implementar conversiones definidas por el usuario entre structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)   
 [Conversiones explícitas definido por el usuario encadenadas en C\#](http://go.microsoft.com/fwlink/?LinkId=112384)