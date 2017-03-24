---
title: "unsafe (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "unsafe_CSharpKeyword"
  - "unsafe"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "unsafe (palabra clave) [C#]"
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# unsafe (Referencia de C#)
La palabra clave `unsafe` denota un contexto no seguro, que es necesario para cualquier operación que involucre a punteros.  Para obtener más información, vea [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
 Se puede utilizar el modificador `unsafe` en la declaración de un tipo o un miembro.  Toda la extensión textual del tipo o del miembro se considera, por lo tanto, como contexto no seguro.  Por ejemplo, el siguiente método se ha declarado con el modificador `unsafe`:  
  
```  
  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 El ámbito del contexto no seguro se extiende desde la lista de parámetros hasta el final del método, de modo que también se pueden utilizar punteros en la lista de parámetros:  
  
```  
  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 También puede utilizar un bloque no seguro para habilitar el uso de código no seguro dentro del mismo.  Por ejemplo:  
  
```  
  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 Para compilar código no seguro, se debe especificar la opción [\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) del compilador.  Common Language Runtime no puede comprobar el código no seguro.  
  
## Ejemplo  
 [!code-cs[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [fixed \(Instrucción\)](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Búferes de tamaño fijo](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)