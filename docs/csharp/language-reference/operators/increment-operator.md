---
title: Operador ++ (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: a52f614ce1bbfb8e9d9be686b277c1e69f6f9d35
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44180938"
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

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)
