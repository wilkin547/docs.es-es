---
title: Operador ++ (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: 0fe1150ca7267d02feeab33168eab7f79734c2a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>Operador ++ (Referencia de C#)
El operador de incremento (`++`) incrementa su operando en 1. El operador de incremento puede aparecer antes o después de su operando: `++variable` y `variable++`.  
  
## <a name="remarks"></a>Comentarios  
 La primera forma es una operación de incremento de prefijo. El resultado de la operación es el valor del operando después del incremento.  
  
 La segunda forma es una operación de incremento de postfijo. El resultado de la operación es el valor del operando antes del incremento.  
  
 Los tipos numéricos y de enumeración poseen operadores de incremento predefinidos. Los tipos definidos por el usuario pueden sobrecargar el operador `++` . Las operaciones de tipos enteros suelen estar permitidas en la enumeración.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
