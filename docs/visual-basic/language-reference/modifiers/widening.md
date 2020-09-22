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
ms.openlocfilehash: 14e0b026f4fc3b0bf202ea643a28d6f1a7df2b7c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867640"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)

Indica que un operador de conversión ( `CType` ) convierte una clase o estructura en un tipo que puede contener todos los valores posibles de la clase o estructura original.  
  
## <a name="converting-with-the-widening-keyword"></a>Convertir con la palabra clave Widening  

 El procedimiento de conversión debe especificar además `Public Shared` de `Widening` .  
  
 Las conversiones de ampliación siempre se realizan correctamente en tiempo de ejecución y nunca provocan pérdida de datos. Por ejemplo `Single` , para, `Double` `Char` `String` y un tipo derivado a su tipo base. Esta última conversión es ampliable porque el tipo derivado contiene todos los miembros del tipo base y, por tanto, es una instancia del tipo base.  
  
 El código utilizado no tiene que usar para las `CType` conversiones de ampliación, incluso si `Option Strict` es `On` .  
  
 La `Widening` palabra clave se puede usar en este contexto:  
  
 [Operator Statement](../statements/operator-statement.md)  
  
 Para obtener definiciones de ejemplo de operadores de conversión de ampliación y de restricción, vea [Cómo: definir un operador de conversión](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>Consulte también

- [Operator Statement](../statements/operator-statement.md)
- [Narrowing](narrowing.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Procedimiento para definir un operador](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../functions/ctype-function.md)
- [Option Strict (instrucción)](../statements/option-strict-statement.md)
- [Procedimiento para definir un operador de conversión](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
