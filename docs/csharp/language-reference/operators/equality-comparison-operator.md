---
title: Operador == (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: f8356320817771cb559192c1ce720a80bf33bbf9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>Operador == (Referencia de C#)
Para los tipos de valor predefinidos, el operador de igualdad (`==`) devuelve True si los valores de sus operandos son iguales, `false` en caso contrario. Para los tipos de referencia diferentes de [string](../../../csharp/language-reference/keywords/string.md), `==` devuelve `true` si sus dos operandos hacen referencia al mismo objeto. Para el tipo `string`, `==` compara los valores de las cadenas.  
  
## <a name="remarks"></a>Comentarios  
 Los tipos de valor definidos por el usuario pueden sobrecargar el operador `==` (vea [operator](../../../csharp/language-reference/keywords/operator.md)). Al igual que los tipos de referencia definidos por el usuario, aunque de manera predeterminada `==` se comporta como se ha descrito anteriormente para los tipos de referencia definidos por el usuario y predefinidos. Si `==` está sobrecargado, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) también debe estar sobrecargado. Las operaciones de tipos enteros suelen estar permitidas en la enumeración.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
