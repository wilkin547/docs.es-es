---
title: Widening (Visual Basic)
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
ms.openlocfilehash: d7d43d4f5f931881d5c8b663c719fe7f92559799
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778669"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)
Indica que un operador de conversión (`CType`) convierte una clase o estructura en un tipo que puede contener todos los valores posibles de la clase o estructura original.  
  
## <a name="converting-with-the-widening-keyword"></a>Convertir con la palabra clave ampliación  
 Debe especificar el procedimiento de conversión `Public Shared` además `Widening`.  
  
 Conversiones de ampliación siempre se realizan correctamente en tiempo de ejecución y nunca incurrir en pérdida de datos. Algunos ejemplos son `Single` a `Double`, `Char` a `String`y un tipo derivado a su tipo base. Esta última conversión es de ampliación ya que el tipo derivado contiene a todos los miembros del tipo base y, por tanto, es una instancia del tipo base.  
  
 El código usado no tiene que usar `CType` para conversiones de ampliación, incluso si `Option Strict` es `On`.  
  
 El `Widening` palabra clave se puede usar en este contexto:  
  
 [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 Por ejemplo ver definiciones de los operadores de conversión de restricción y ampliación [Cómo: Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>Vea también

- [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Cómo: Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Función CType](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Cómo: Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
