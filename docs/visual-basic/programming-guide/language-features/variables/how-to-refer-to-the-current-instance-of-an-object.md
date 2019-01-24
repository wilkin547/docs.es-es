---
title: Procedimiento Hacer referencia a la instancia actual de un objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: d166ce62a2bb0522d1ca7011aeff7afe076c2d8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542202"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Procedimiento Hacer referencia a la instancia actual de un objeto (Visual Basic)
El *instancia actual* de un objeto es la instancia en la que se está ejecutando el código.  
  
 Usa el `Me` palabra clave para hacer referencia a la instancia actual.  
  
### <a name="to-refer-to-the-current-instance"></a>Para hacer referencia a la instancia actual  
  
-   Utilice el `Me` palabra clave donde utilizaría normalmente el nombre de una variable de objeto.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Aunque `Me` se comporta como un objeto variable, no puede declararla ni asignarle nada. `Me` siempre se hace referencia a la instancia actual.  
  
## <a name="see-also"></a>Vea también
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
