---
title: Procedimiento Movimiento de datos dentro y fuera de una Variable (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: 9b34173ebb3226fa00610c124c7b680e18d80de9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717953"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Procedimiento Movimiento de datos dentro y fuera de una Variable (Visual Basic)
Almacenar un valor en una variable colocando el nombre de variable en el lado izquierdo de una instrucción de asignación.  
  
## <a name="putting-data-in-a-variable"></a>Colocación de datos en una Variable  
  
#### <a name="to-store-a-value-in-a-variable"></a>Para almacenar un valor en una variable  
  
-   Utilice el nombre de variable en el lado izquierdo de una instrucción de asignación.  
  
     En el ejemplo siguiente se establece el valor de la variable `alpha`.  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     El valor generado en el lado derecho de la instrucción de asignación se almacena en la variable.  
  
## <a name="getting-data-from-a-variable"></a>Obtener datos de una Variable  
 Recuperar el valor de una variable mediante la inclusión del nombre de variable en una expresión.  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a>Para recuperar un valor de una variable  
  
-   Utilice el nombre de variable en una expresión. Puede usar una variable en cualquier lugar puede usar una constante o un literal, excepto en una expresión que define el valor de una constante.  
  
     O bien  
  
-   Utilice el nombre de variable siguiendo la igual (`=`) inicie sesión en una instrucción de asignación.  
  
     En el ejemplo siguiente se lee el valor de la variable `startValue` y, a continuación, usa el valor de la variable `counter` en una expresión.  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     El valor de la variable participa en la expresión tal como haría una constante y, a continuación, se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.  
  
## <a name="see-also"></a>Vea también
- [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
