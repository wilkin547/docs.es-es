---
title: "Operador / (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/ (operador) [C#]"
  - "operador de división [C#]"
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Operador / (Referencia de C#)
El operador de división \(`/`\) permite dividir su primer operando por su segundo operando.  Todos los tipos numéricos poseen operadores de división predefinidos.  
  
## Comentarios  
 Los tipos definidos por el usuario pueden sobrecargar el operador `/` \(vea [operador](../../../csharp/language-reference/keywords/operator.md)\).  Una sobrecarga del operador `/`, sobrecarga implícitamente el [operador \/\=](../../../csharp/language-reference/operators/subtraction-assignment-operator.md).  
  
 El resultado de dividir dos enteros siempre es un número entero.  Por ejemplo, el resultado de 7 \/ 3 es 2.  Para determinar el resto de 7 \/ 3, utilice el operador de resto \([%](../../../csharp/language-reference/operators/modulus-operator.md)\).  Para obtener un cociente como un número racional o fracción, asigne al dividendo o al divisor el tipo `float` o el tipo `double`.  Puede asignar al tipo de forma implícita si express el dividendo o el divisor como decimal, poniendo un dígito a la derecha del separador decimal, como se muestra en el ejemplo siguiente.  
  
## Ejemplo  
 [!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)