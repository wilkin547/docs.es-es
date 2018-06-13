---
title: 'Cómo: Introducir y extraer los datos de una variable (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: bfda451cefff699561253910715d8450414b00ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650873"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Cómo: Introducir y extraer los datos de una variable (Visual Basic)
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
 Recupera el valor de una variable incluyendo el nombre de variable en una expresión.  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a>Para recuperar un valor de una variable  
  
-   Utilice el nombre de variable en una expresión. Puede utilizar una variable en cualquier lugar puede usar una constante o un literal, excepto en una expresión que define el valor de una constante.  
  
     -o bien-  
  
-   Utilice el nombre de variable siguiendo la igual (`=`) iniciar sesión en una instrucción de asignación.  
  
     En el ejemplo siguiente se lee el valor de la variable `startValue` y, a continuación, usa el valor de la variable `counter` en una expresión.  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     El valor de la variable participa en la expresión tal como haría una constante y, a continuación, se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.  
  
## <a name="see-also"></a>Vea también  
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
