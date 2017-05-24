---
title: void (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- void_CSharpKeyword
- void
dev_langs:
- CSharp
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
caps.latest.revision: 15
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
ms.openlocfilehash: b4aa3c7c54e5e4d53975262adbbd9b54c701a69e
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="void-c-reference"></a>void (Referencia de C#)
Cuando se usa como tipo de valor devuelto para un método, `void` especifica que el método no devuelve un valor.  
  
 `void` no se permite en la lista de parámetros de un método. Un método que no usa parámetros y que no devuelve ningún valor se declara del siguiente modo:  
  
```  
public void SampleMethod()  
{  
    // Body of the method.  
}  
```  
  
 `void` también se usa en un contexto no seguro para declarar un puntero a un tipo desconocido. Para obtener más información, vea [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).  
  
 `void` es un alias para el tipo <xref:System.Void?displayProperty=fullName> de .NET Framework.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md)   
 [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)

