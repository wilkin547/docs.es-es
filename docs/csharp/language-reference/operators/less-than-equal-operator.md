---
title: Operador &lt;= (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
ms.openlocfilehash: afbb932c1be010790236bec73a36acf0f01b97f4
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44270213"
---
# <a name="lt-operator-c-reference"></a>Operador &lt;= (Referencia de C#)
Todos los tipos de enumeración y numéricos definen un operador relacional "menor o igual que" (`<=`), que devuelve `true` si el primer operando es menor o igual que el segundo; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Los tipos definidos por el usuario pueden sobrecargar el operador `<=`. Para obtener más información, vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md). Si `<=` está sobrecargado, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) también debe estar sobrecargado. Las operaciones de tipos enteros suelen estar permitidas en la enumeración.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)  
- [explicit](../../../csharp/language-reference/keywords/explicit.md)
