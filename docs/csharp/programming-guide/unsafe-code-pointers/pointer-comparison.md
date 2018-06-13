---
title: Comparación de punteros (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: af264cd1572faafe25ee170b35cbeb48ed0fb2aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337709"
---
# <a name="pointer-comparison-c-programming-guide"></a>Comparación de punteros (Guía de programación de C#)
Puede aplicar los siguientes operadores para comparar los punteros de cualquier tipo:  
  
 **==   !=   \<   >   \<=   >=**  
  
 Los operadores de comparación comparan las direcciones de los dos operandos, como si fueran enteros sin signo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_2.cs)]  
  
## <a name="sample-output"></a>Resultados del ejemplo  
 `True`  
  
 `False`  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)  
 [Manipular punteros](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Tipos](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
