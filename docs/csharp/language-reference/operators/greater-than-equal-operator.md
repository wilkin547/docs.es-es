---
title: 'Operador &gt;=: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
ms.openlocfilehash: 9bea9034d2998a589fefca19f41444c9aced6e13
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237719"
---
# <a name="gt-operator-c-reference"></a>Operador &gt;= (Referencia de C#)
Todos los tipos de enumeración y numéricos definen un operador relacional "mayor o igual que", `>=`, que devuelve `true` si el primer operando es mayor o igual que el segundo, `false` de otro modo.  
  
## <a name="remarks"></a>Comentarios  
 Los tipos definidos por el usuario pueden sobrecargar el operador `>=`. Para obtener más información, vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md). Si `>=` está sobrecargado, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) también debe estar sobrecargado. Las operaciones de tipos enteros suelen estar permitidas en la enumeración.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)
