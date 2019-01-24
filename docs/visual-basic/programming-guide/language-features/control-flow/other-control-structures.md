---
title: Estructuras de control adicionales (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: a383d0c95de5286cce722c05bd8888d5acffb173
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590005"
---
# <a name="other-control-structures-visual-basic"></a>Estructuras de control adicionales (Visual Basic)
Visual Basic proporciona estructuras de control que le ayudarán a deshacerse de un recurso o reducen el número de veces que tiene que repetir una referencia de objeto.  
  
## <a name="usingend-using-construction"></a>Usar... Extremo usando la construcción  
 El `Using...End Using` construcción establece un bloque de instrucciones dentro del cual el uso de un recurso como una conexión SQL. Opcionalmente, puede adquirir el recurso con el `Using` instrucción. Al salir el `Using` bloque, Visual Basic elimina automáticamente del recurso para que esté disponible para otro código para usar. El recurso debe ser local y descartable. Para obtener más información, vea [Using (Instrucción)](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>Con... Terminar con la construcción  
 El `With...End With` le permite especificar una referencia de objeto una vez y, a continuación, ejecutar una serie de instrucciones que tienen acceso a sus miembros. Esto puede simplificar el código y mejorar el rendimiento porque Visual Basic no tiene que volver a establecer la referencia para cada instrucción que tiene acceso a él. Para obtener más información, consulte [con... Terminar con la instrucción](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>Vea también
- [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Estructuras de decisión](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Estructuras de control anidadas](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Using (instrucción)](../../../../visual-basic/language-reference/statements/using-statement.md)
- [With...End With (instrucción)](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
