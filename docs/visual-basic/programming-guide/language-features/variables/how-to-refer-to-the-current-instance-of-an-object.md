---
description: 'Más información sobre: Cómo: hacer referencia a la instancia actual de un objeto (Visual Basic)'
title: Procedimiento para hacer referencia a la instancia actual de un objeto
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 84a52c9d0a8b1f588630b31d022490f37595850d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481745"
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
  
## <a name="see-also"></a>Consulte también

- [Variables de objeto](object-variables.md)
- [Asignación de variables de objeto](object-variable-assignment.md)
- [Me, My, MyBase y MyClass](../../program-structure/me-my-mybase-and-myclass.md)
