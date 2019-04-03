---
title: 'Declaración de un operador debe ser uno de: +,-, *,-, -, ^, &amp;, Like, Mod y, Or, Xor, no, <<>>,, =, <>, <, < =, >, > =, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: dac8613d79e3262e4d1fd6ad1599fd01182e329b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819377"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a>Declaración de un operador debe ser uno de: +,-, *,\,/, ^, &amp;, Like, Mod y, Or, Xor, no, \< \<, >>...
Puede declarar sólo un operador que sea apto para la sobrecarga. En la tabla siguiente se enumera los operadores que se puede declarar.  
  
|Tipo|Operadores|  
|----------|---------------|  
|Unario|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Conversión (unaria)|`CType`|  
  
 Tenga en cuenta que el `=` operador en la lista binaria es el operador de comparación, no el operador de asignación.  
  
 **Identificador de error:** BC33000  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Seleccione un operador del conjunto de operadores sobrecargables.  
  
2.  Si necesita la función de sobrecarga de un operador que no se puede sobrecargar directamente, cree un procedimiento `Function` que tome los parámetros adecuados y devuelva el valor adecuado.  
  
## <a name="see-also"></a>Vea también

- [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Cómo: Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Cómo: Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
