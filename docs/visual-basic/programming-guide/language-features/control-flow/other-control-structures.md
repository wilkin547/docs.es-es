---
title: Estructuras de control adicionales
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 758df361f421684655147ae288af3f350e53c4d7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348135"
---
# <a name="other-control-structures-visual-basic"></a>Estructuras de control adicionales (Visual Basic)
Visual Basic proporciona estructuras de control que le ayudan a desechar un recurso o a reducir el número de veces que tiene que repetir una referencia de objeto.  
  
## <a name="usingend-using-construction"></a>Usar... End using  
 La construcción `Using...End Using` establece un bloque de instrucciones en el que se hace uso de un recurso como una conexión SQL. Opcionalmente, puede adquirir el recurso con la instrucción `Using`. Al salir del bloque `Using`, Visual Basic desecha automáticamente el recurso para que esté disponible para que lo use otro código. El recurso debe ser local y descartable. Para obtener más información, vea [Using (Instrucción)](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>Con... End with (construcción)  
 La construcción `With...End With` permite especificar una sola referencia de objeto y, a continuación, ejecutar una serie de instrucciones que tienen acceso a sus miembros. Esto puede simplificar el código y mejorar el rendimiento, ya que Visual Basic no tiene que volver a establecer la referencia para cada instrucción que tiene acceso a ella. Para obtener más información, vea [con... End with](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>Vea también

- [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Estructuras de decisión](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Estructuras de control anidadas](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Using (instrucción)](../../../../visual-basic/language-reference/statements/using-statement.md)
- [With...End With (instrucción)](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
