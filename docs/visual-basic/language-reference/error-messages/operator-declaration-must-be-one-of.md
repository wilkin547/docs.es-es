---
title: 'La declaración del operador debe ser uno de los siguientes: +,-, *,-,-, ^, &amp; , like, mod, and, or, XOR, not,  <<,  >>, =,  <>, <, <=, >, >=, ctype, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: c388b1b0762dd7475ca365a8a62228d0b5d59414
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873616"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a>La declaración del operador debe ser uno de los siguientes: +,-, *, \, /, ^, &amp; , like, mod, and, or, XOR, not, \<\<, >>...

Solo puede declarar un operador que sea válido para la sobrecarga. En la tabla siguiente se enumeran los operadores que se pueden declarar.  
  
|Tipo|Operadores|  
|----------|---------------|  
|Unario|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Conversión (unaria)|`CType`|  
  
 Tenga en cuenta que el `=` operador de la lista binaria es el operador de comparación, no el operador de asignación.  
  
 **Identificador de error:** BC33000  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Seleccione un operador del conjunto de operadores sobrecargables.  
  
2. Si necesita la función de sobrecarga de un operador que no se puede sobrecargar directamente, cree un procedimiento `Function` que tome los parámetros adecuados y devuelva el valor adecuado.  
  
## <a name="see-also"></a>Consulte también

- [Operator Statement](../statements/operator-statement.md)
- [Procedimientos de operador](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Procedimiento para definir un operador](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Procedimiento para definir un operador de conversión](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Instrucción Function](../statements/function-statement.md)
