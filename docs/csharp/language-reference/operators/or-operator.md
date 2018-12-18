---
title: 'Operador|: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 19a37bbb54d2ef3e15e4465df05c9b6df705206c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240364"
---
# <a name="-operator-c-reference"></a>Operador | (Referencia de C#)
Los operadores binarios `|` están predefinidos para los tipos enteros y `bool`. Para los tipos enteros, `|` calcula OR bit a bit de sus operandos. Para operandos `bool`, `|` calcula el OR lógico de sus operandos; es decir, el resultado es `false` si y solo si ambos operandos son `false`.  
  
## <a name="remarks"></a>Comentarios  
 El operador `|` binario evalúa ambos operandos con independencia del valor del primero, a diferencia del [operador OR condicional](conditional-or-operator.md) `||`.
 
 Los tipos definidos por el usuario pueden sobrecargar el operador `|` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)
