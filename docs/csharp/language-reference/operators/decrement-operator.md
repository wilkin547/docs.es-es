---
title: Operador -- (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4eb68143103d44defeac7191e7c4ce7d1ee90e9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="---operator-c-reference"></a>Operador -- (Referencia de C#)
El operador de decremento (`--`) disminuye su operando en 1. El operador de decremento puede aparecer antes o después de su operando: `--variable` y `variable--`. La primera forma es una operación de decremento de prefijo. El resultado de la operación es el valor del operando "después" del decremento. La segunda forma es una operación de decremento de postfijo. El resultado de la operación es el valor del operando "antes" del decremento.  
  
## <a name="remarks"></a>Comentarios  
 Los tipos numéricos y de enumeración tienen operadores de decremento predefinidos.  
  
 Los tipos definidos por el usuario pueden sobrecargar el operador `--` (vea [operator](../../../csharp/language-reference/keywords/operator.md)). Las operaciones de tipos enteros suelen estar permitidas en la enumeración.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
