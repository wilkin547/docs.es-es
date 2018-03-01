---
title: + Operador (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b15d5d1a304569b92b2f811a9ea714e4b30d60d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Operador + (Referencia de C#)
El operador `+` puede funcionar como un operador unario o binario.  
  
## <a name="remarks"></a>Comentarios  
 Los operadores unarios `+` están predefinidos para todos los tipos numéricos. El resultado de una operación `+` unaria en un tipo numérico es simplemente el valor del operando.  
  
 Los operadores binarios `+` están predefinidos para tipos numéricos y de cadena. Para los tipos numéricos, + calcula la suma de sus dos operandos. Cuando uno o ambos operandos son de tipo cadena, + concatena las representaciones de cadena de los operandos.  
  
 Los tipos de delegado también proporcionan un operador `+` binario, que realiza la concatenación de delegados.  
  
 Los tipos definidos por el usuario pueden sobrecargar los operadores `+` unarios y `+` binarios. Las operaciones de tipos enteros suelen estar permitidas en la enumeración. Para más información, vea [Operador (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)  
 [Operador (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md)
