---
title: "params (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "params_CSharpKeyword"
  - "params"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "parámetros [C#], params"
  - "params (palabra clave) [C#]"
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# params (Referencia de C#)
Usando la palabra clave `params`, puede especificar un [parámetro de método](../../../csharp/language-reference/keywords/method-parameters.md) que acepta un número variable de argumentos.  
  
 Puede enviar una lista separada por comas de argumentos del tipo especificado en la declaración de parámetro o en una matriz de argumentos del tipo especificado.  También puede no enviar ningún argumento.  Si no se envía ningún argumento, la longitud de la lista de `params` es cero.  
  
 No se permiten parámetros adicionales después de la palabra clave `params`, ni varias palabras clave `params` en una misma declaración de método.  
  
## Ejemplo  
 En el siguiente ejemplo se muestran varias maneras de enviar argumentos a un parámetro `params`.  
  
 [!code-cs[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Parámetros de métodos](../../../csharp/language-reference/keywords/method-parameters.md)