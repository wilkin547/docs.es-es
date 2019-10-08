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
ms.openlocfilehash: 6c216dbc59bcad7a9f24bb01f856c3d29c288dbb
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005657"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Procedimiento Hacer referencia a la instancia actual de un objeto (Visual Basic)
La *instancia actual* de un objeto es la instancia en la que se está ejecutando el código.  
  
 Use la palabra clave `Me` para hacer referencia a la instancia actual.  
  
### <a name="to-refer-to-the-current-instance"></a>Para hacer referencia a la instancia actual  
  
- Use la palabra clave `Me` en la que usaría normalmente el nombre de una variable de objeto.  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Aunque `Me` se comporta como una variable de objeto, no se puede declarar ni asignar nada. `Me` siempre hace referencia a la instancia actual.  
  
## <a name="see-also"></a>Vea también

- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
