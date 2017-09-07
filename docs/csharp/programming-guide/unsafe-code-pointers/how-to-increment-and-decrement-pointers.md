---
title: "Cómo: Aumentar y disminuir punteros (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: 20
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b474249ed9f7778e44981b292d51f29f46bc420d
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a>Cómo: Aumentar y disminuir punteros (Guía de programación de C#)
Use los operadores de incremento y decremento, `++` y `--`, para cambiar la ubicación del puntero en [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) para un puntero de tipo pointer-type*. Las expresiones de incremento y decremento adquieren la forma siguiente:  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 Los operadores de incremento y decremento se pueden aplicar a punteros de cualquier tipo, a excepción del tipo `void*`.  
  
 El efecto de aplicar el operador de incremento a un puntero del tipo `pointer-type` es agregar [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) a la dirección que está en la variable del puntero.  
  
 El efecto de aplicar el operador de decremento a un puntero del tipo `pointer-type` es restar `sizeof` (`pointer-type`) de la dirección que está en la variable del puntero.  
  
 No se genera ninguna excepción cuando la operación desborda el dominio del puntero y el resultado depende de la implementación.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se avanza a través de una matriz incrementando el puntero según el tamaño de `int`. Con cada paso que avanza, se muestra la dirección y el contenido del elemento de matriz.  
  
 [!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
 **Value:0 @ Address:12860272**  
**Value:1 @ Address:12860276**  
**Value:2 @ Address:12860280**  
**Value:3 @ Address:12860284**  
**Value:4 @ Address:12860288**   
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)   
 [Manipulación de punteros](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)   
 [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Tipos](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)

