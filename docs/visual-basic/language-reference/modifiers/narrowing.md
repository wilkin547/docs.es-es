---
title: Narrowing
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: b252f7939e812f31103d4bd98ffd50953679f042
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351474"
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)
Indica que un operador de conversión (`CType`) convierte una clase o estructura en un tipo que podría no contener algunos de los valores posibles de la clase o estructura original.  
  
## <a name="converting-with-the-narrowing-keyword"></a>Convertir con la palabra clave narrowing  
 El procedimiento de conversión debe especificar `Public Shared` además de `Narrowing`.  
  
 Las conversiones de restricción no siempre se realizan correctamente en tiempo de ejecución y pueden producir un error o provocar la pérdida de datos. Algunos ejemplos son `Long` `Integer`, `String` a `Date`y un tipo base a un tipo derivado. Esta última conversión está restringida porque el tipo base no puede contener todos los miembros del tipo derivado y, por tanto, no es una instancia del tipo derivado.  
  
 Si `Option Strict` es `On`, el código de consumo debe usar `CType` para todas las conversiones de restricción.  
  
 La palabra clave `Narrowing` se puede usar en este contexto:  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a>Vea también

- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Widening](../../../visual-basic/language-reference/modifiers/widening.md)
- [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Función CType](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
