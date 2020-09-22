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
ms.openlocfilehash: 77515357ac9dc972992df09c471695aad13985c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867938"
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)

Indica que un operador de conversión ( `CType` ) convierte una clase o estructura en un tipo que podría no contener algunos de los valores posibles de la clase o estructura original.  
  
## <a name="converting-with-the-narrowing-keyword"></a>Convertir con la palabra clave narrowing  

 El procedimiento de conversión debe especificar además `Public Shared` de `Narrowing` .  
  
 Las conversiones de restricción no siempre se realizan correctamente en tiempo de ejecución y pueden producir un error o provocar la pérdida de datos. Por ejemplo `Long` , para, `Integer` `String` `Date` y un tipo base para un tipo derivado. Esta última conversión está restringida porque el tipo base no puede contener todos los miembros del tipo derivado y, por tanto, no es una instancia del tipo derivado.  
  
 Si `Option Strict` es `On` , el código utilizado debe usar `CType` para todas las conversiones de restricción.  
  
 La `Narrowing` palabra clave se puede usar en este contexto:  
  
 [Operator Statement](../statements/operator-statement.md)  
  
## <a name="see-also"></a>Consulte también

- [Operator Statement](../statements/operator-statement.md)
- [Widening](widening.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Procedimiento para definir un operador](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../functions/ctype-function.md)
- [Option Strict (instrucción)](../statements/option-strict-statement.md)
