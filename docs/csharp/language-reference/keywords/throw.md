---
title: "throw (Referencia de C#) | Microsoft Docs"
ms.date: "2015-03-02"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "throw"
  - "throw_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "throw (palabra clave) [C#]"
  - "throw (instrucción) [C#]"
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
caps.handback.revision: 22
---
# throw (Referencia de C#)
La instrucción `throw` se usa para indicar una situación anómala \(excepción\) durante la ejecución del programa.  
  
## Comentarios  
 La excepción iniciada es un objeto cuya clase se deriva de <xref:System.Exception?displayProperty=fullName>, como se muestra en el ejemplo siguiente.  
  
```  
class MyException : System.Exception {}  
// ...  
throw new MyException();  
```  
  
 Normalmente, la instrucción `throw` se usa con las instrucciones `try-catch` o `try-finally`.  Se puede usar una instrucción [throw](../../../csharp/language-reference/keywords/throw.md) en un bloque `catch` para volver a iniciar la excepción detectada por el bloque `catch`.  En este caso, la instrucción [throw](../../../csharp/language-reference/keywords/throw.md) no toma un operando de excepción.  Para obtener más información y ejemplos, vea [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) y [Cómo: Iniciar excepciones explícitamente](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md).  
  
## Ejemplo  
 En este ejemplo se muestra cómo iniciar una excepción mediante la instrucción `throw`.  
  
 [!code-cs[csrefKeywordsExceptions#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/throw_1.cs)]  
  
## Ejemplo de código  
 Consulte los ejemplos en [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) y [Cómo: Iniciar excepciones explícitamente](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [Instrucciones try, catch y throw en C\+\+](../../../csharp/language-reference/keywords/try-catch.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Instrucciones para el control de excepciones](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [Cómo: Iniciar excepciones explícitamente](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md)