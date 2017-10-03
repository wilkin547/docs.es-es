---
title: + Operador (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5455375148f1924c7fe1cdb10e7924abb83a1565
ms.contentlocale: es-es
ms.lasthandoff: 09/25/2017

---
# <a name="-operator-c-reference"></a>Operador + (Referencia de C#)
El operador `+` puede funcionar como un operador unario o binario.  
  
## <a name="remarks"></a>Comentarios  
 Los operadores unarios `+` están predefinidos para todos los tipos numéricos. El resultado de una operación `+` unaria en un tipo numérico es simplemente el valor del operando.  
  
 Los operadores binarios `+` están predefinidos para tipos numéricos y de cadena. Para los tipos numéricos, + calcula la suma de sus dos operandos. Cuando uno o ambos operandos son de tipo cadena, + concatena las representaciones de cadena de los operandos.  
  
 Los tipos de delegado también proporcionan un operador `+` binario, que realiza la concatenación de delegados.  
  
 Los tipos definidos por el usuario pueden sobrecargar los operadores `+` unarios y `+` binarios. Las operaciones de tipos enteros suelen estar permitidas en la enumeración. Para más información, vea [Operador (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)   
 [Operador (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md)

