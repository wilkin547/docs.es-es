---
title: 'Cómo: Hacer referencia a la instancia actual de un objeto (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: c1b79f1b6a9768941d6fe966c5b5886ea742f808
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Cómo: Hacer referencia a la instancia actual de un objeto (Visual Basic)
El *instancia actual* de un objeto es la instancia en la que se esté ejecutando el código.  
  
 Usa el `Me` palabra clave para hacer referencia a la instancia actual.  
  
### <a name="to-refer-to-the-current-instance"></a>Para hacer referencia a la instancia actual  
  
-   Utilice la `Me` palabra clave donde utilizaría normalmente el nombre de una variable de objeto.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Aunque `Me` se comporta como un objeto variable, no puede declararla ni asignarle nada. `Me` siempre hace referencia a la instancia actual.  
  
## <a name="see-also"></a>Vea también  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
