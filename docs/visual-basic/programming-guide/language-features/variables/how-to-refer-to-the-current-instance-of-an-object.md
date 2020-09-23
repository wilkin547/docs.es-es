---
title: Procedimiento para hacer referencia a la instancia actual de un objeto
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 64d21fe4aaf6fd34bf880373a7ab3067fb67820e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077064"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Cómo: Hacer referencia a la instancia actual de un objeto (Visual Basic)

La *instancia actual* de un objeto es la instancia en la que se está ejecutando el código.  
  
 La `Me` palabra clave se usa para hacer referencia a la instancia actual.  
  
### <a name="to-refer-to-the-current-instance"></a>Para hacer referencia a la instancia actual  
  
- Use la `Me` palabra clave donde normalmente usaría el nombre de una variable de objeto.  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Aunque se `Me` comporta como una variable de objeto, no se puede declarar ni asignar nada. `Me` siempre hace referencia a la instancia actual.  
  
## <a name="see-also"></a>Vea también

- [Variables de objeto](object-variables.md)
- [Asignación de variables de objeto](object-variable-assignment.md)
- [Me, My, MyBase y MyClass](../../program-structure/me-my-mybase-and-myclass.md)
