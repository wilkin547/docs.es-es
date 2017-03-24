---
title: "is (Referencia de C#) | Microsoft Docs"
ms.date: "2017-02-17"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "is_CSharpKeyword"
  - "is"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "is (palabra clave) [C#]"
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# is (Referencia de C#)
Comprueba si un objeto es compatible con un tipo determinado.  Por ejemplo, el código siguiente puede determinar si un objeto es una instancia del tipo `MyObject` o un tipo que se deriva de `MyObject`:  
  
```  
if (obj is MyObject)  
{  
}  
```  
  
 Una expresión `is` se evalúa como `true` si la expresión proporcionada no es NULL y el objeto proporcionado se puede convertir al tipo proporcionado sin producir una excepción.  
  
 La palabra clave `is` genera una advertencia en tiempo de compilación si se sabe que la expresión siempre será `true` o siempre será `false`, pero normalmente evalúa la compatibilidad de tipos en tiempo de ejecución.  
  
 El operador `is` no se puede sobrecargar.  
  
 Observe que el operador `is` solamente tiene en cuenta las conversiones de referencia, las conversiones boxing y las conversiones unboxing.  No se tienen en cuenta otras conversiones, tales como las conversiones definidas por el usuario.  
  
 No se permite el uso de métodos anónimos en el lado izquierdo del operador `is`.  Esta excepción incluye expresiones lambda.  
  
## Ejemplo  
 [!code-cs[csrefKeywordsOperator#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/is_1.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [typeof](../../../csharp/language-reference/keywords/typeof.md)   
 [as](../../../csharp/language-reference/keywords/as.md)   
 [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)