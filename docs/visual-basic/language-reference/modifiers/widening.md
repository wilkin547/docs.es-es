---
title: Widening
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 1c9aa78549ca6e41c9fe54c12e0aaec8e7cc30cb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347829"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)
Indica que un operador de conversión (`CType`) convierte una clase o estructura en un tipo que puede contener todos los valores posibles de la clase o estructura original.  
  
## <a name="converting-with-the-widening-keyword"></a>Convertir con la palabra clave Widening  
 El procedimiento de conversión debe especificar `Public Shared` además de `Widening`.  
  
 Las conversiones de ampliación siempre se realizan correctamente en tiempo de ejecución y nunca provocan pérdida de datos. Los ejemplos se `Single` para `Double`, `Char` a `String`y un tipo derivado a su tipo base. Esta última conversión es ampliable porque el tipo derivado contiene todos los miembros del tipo base y, por tanto, es una instancia del tipo base.  
  
 El código utilizado no tiene que utilizar `CType` para las conversiones de ampliación, aunque se `On``Option Strict`.  
  
 La palabra clave `Widening` se puede usar en este contexto:  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 Para obtener definiciones de ejemplo de operadores de conversión de ampliación y de restricción, vea [Cómo: definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>Vea también

- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Función CType](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
