---
title: 'Comparación de punteros: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: 72d9017064959c801bd2702ff585ee16b1592da6
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236796"
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

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)  
- [Manipular punteros](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [Tipos](../../../csharp/language-reference/keywords/types.md)  
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
- [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
