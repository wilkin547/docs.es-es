---
title: 'Declaración del operador debe ser uno de: +,-, *,-, -, ^, &amp;, Like, Mod y, Or, Xor, no es así, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;= &gt; , &gt;=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: eb1e7e8088ec8661be2469aff043c0f1a96e4d01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595025"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a>Declaración del operador debe ser uno de: +,-, *,\,/, ^, &amp;, Like, Mod y, Or, Xor, no es así, &lt; &lt;, &gt; &gt;...
Puede declarar solo un operador que es apto para la sobrecarga. En la tabla siguiente se enumera los operadores que se puede declarar.  
  
|Tipo|Operadores|  
|----------|---------------|  
|Unario|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Conversión (unaria)|`CType`|  
  
 Tenga en cuenta que la `=` en la lista binaria es el operador de comparación, no el operador de asignación.  
  
 **Id. de error:** BC33000  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Seleccione un operador del conjunto de operadores sobrecargables.  
  
2.  Si necesita la función de sobrecarga de un operador que no se puede sobrecargar directamente, cree un procedimiento `Function` que tome los parámetros adecuados y devuelva el valor adecuado.  
  
## <a name="see-also"></a>Vea también  
 [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
