---
title: "Cómo: Introducir y extraer los datos de una variable (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fefb1979e35cd7b5fa1917f8f1a57af575e51234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
  
     O bien  
  
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
