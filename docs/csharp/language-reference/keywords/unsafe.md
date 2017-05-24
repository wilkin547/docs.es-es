---
title: unsafe (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
dev_langs:
- CSharp
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: afedd3d99aea9f73d175fd2957a7d586ebce6d72
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="unsafe-c-reference"></a>unsafe (Referencia de C#)
La palabra clave `unsafe` denota un contexto no seguro, que es necesario para realizar cualquier operación que implique punteros. Para obtener más información, vea [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) (Código no seguro y punteros [Guía de programación de C#]).  
  
 Puede usar el codificador `unsafe` en la declaración de un tipo o miembro. Por consiguiente, toda la extensión textual del tipo o miembro se considera un contexto no seguro. Por ejemplo, el siguiente método se declara con el modificador `unsafe`:  
  
```  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 El ámbito del contexto no seguro se extiende desde la lista de parámetros hasta el final del método, por lo que también pueden usarse punteros en la lista de parámetros:  
  
```  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 También puede usarse un bloque no seguro para habilitar el uso de código no seguro en el bloque. Por ejemplo:  
  
```  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 Para compilar código no seguro, debe especificar la opción [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) del compilador. Common Language Runtime no puede comprobar el código no seguro.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md)  (fixed [Instrucción, Referencia de C#])  
 [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  (Código no seguro y punteros [Guía de programación de C#])  
 [Búferes de tamaño fijo](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)

