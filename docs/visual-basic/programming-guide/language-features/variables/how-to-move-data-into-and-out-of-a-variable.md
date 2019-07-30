---
title: Procedimiento Movimiento de datos dentro y fuera de una variable (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: df55f122c4ea029a383196f8d9684295ac8926aa
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631126"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Procedimiento Movimiento de datos dentro y fuera de una variable (Visual Basic)

Para almacenar un valor en una variable, coloque el nombre de la variable en el lado izquierdo de una instrucción de asignación.

## <a name="putting-data-in-a-variable"></a>Colocar datos en una variable

#### <a name="to-store-a-value-in-a-variable"></a>Para almacenar un valor en una variable

- Use el nombre de la variable en el lado izquierdo de una instrucción de asignación.

    En el ejemplo siguiente se establece el valor de `alpha`la variable.

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    El valor generado en el lado derecho de la instrucción de asignación se almacena en la variable.

## <a name="getting-data-from-a-variable"></a>Obtención de datos de una variable

Para recuperar el valor de una variable, incluya el nombre de la variable en una expresión.

#### <a name="to-retrieve-a-value-from-a-variable"></a>Para recuperar un valor de una variable

- Use el nombre de la variable en una expresión. Puede usar una variable en cualquier parte donde pueda usar una constante o un literal, excepto en una expresión que defina el valor de una constante.

  O bien

- Use el nombre de la variable que sigue`=`el signo igual () en una instrucción de asignación.

  En el ejemplo siguiente se lee el valor de `startValue` la variable y, a continuación, se `counter` usa el valor de la variable en una expresión.

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  El valor de la variable participa en la expresión de la misma forma que una constante y, a continuación, se almacena en la variable o la propiedad en el lado izquierdo de la instrucción de asignación.

## <a name="see-also"></a>Vea también

- [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
