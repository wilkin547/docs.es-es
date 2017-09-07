---
title: Operador != (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '!=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
caps.latest.revision: 14
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
ms.openlocfilehash: 49c5c9668c6b1169220ee4fa0babf167292a9813
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Operador != (Referencia de C#)
El operador de desigualdad (`!=`) devuelve false si sus dos operandos son iguales; en caso contrario, devuelve true. Los operadores de desigualdad están predefinidos para todos los tipos, incluidos string y object. Los tipos definidos por el usuario pueden sobrecargar el operador `!=`.  
  
## <a name="remarks"></a>Comentarios  
 Para los tipos de valor predefinidos, el operador de desigualdad (`!=`) devuelve true si los valores de sus operandos son diferentes, y false en caso contrario. Para los tipos de referencia, excepto `string`, `!=` devuelve true si sus dos operandos hacen referencia a objetos diferentes. Para el tipo `string`, `!=` compara los valores de las cadenas.  
  
 Los tipos de valor definidos por el usuario pueden sobrecargar el operador `!=` (vea [operator](../../../csharp/language-reference/keywords/operator.md)). Al igual que los tipos de referencia definidos por el usuario, aunque de manera predeterminada `!=` se comporta como se ha descrito anteriormente para los tipos de referencia definidos por el usuario y predefinidos. Si `!=` está sobrecargado, [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) también debe estar sobrecargado. Las operaciones de tipos enteros suelen estar permitidas en la enumeración.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)

