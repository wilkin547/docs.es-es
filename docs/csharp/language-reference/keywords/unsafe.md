---
title: unsafe (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: c476bdcea4993b27c0e8f8148a985f18a43ba09b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171959"
---
# <a name="unsafe-c-reference"></a>unsafe (Referencia de C#)
La palabra clave `unsafe` denota un contexto no seguro, que es necesario para realizar cualquier operación que implique punteros. Para obtener más información, vea [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) (Código no seguro y punteros [Guía de programación de C#]).  
  
 Puede usar el codificador `unsafe` en la declaración de un tipo o miembro. Por consiguiente, toda la extensión textual del tipo o miembro se considera un contexto no seguro. Por ejemplo, el siguiente método se declara con el modificador `unsafe`:  
  
```csharp  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 El ámbito del contexto no seguro se extiende desde la lista de parámetros hasta el final del método, por lo que también pueden usarse punteros en la lista de parámetros:  
  
```csharp  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 También puede usarse un bloque no seguro para habilitar el uso de código no seguro en el bloque. Por ejemplo:  
  
```csharp  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 Para compilar código no seguro, debe especificar la opción [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) del compilador. Common Language Runtime no puede comprobar el código no seguro.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Búferes de tamaño fijo](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
