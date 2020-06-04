---
title: Estructuras de control adicionales
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: c6d80b237c7c3512c2904547842fdeb3c69bef68
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402023"
---
# <a name="other-control-structures-visual-basic"></a>Estructuras de control adicionales (Visual Basic)
Visual Basic proporciona estructuras de control que le ayudan a desechar un recurso o a reducir el número de veces que tiene que repetir una referencia de objeto.  
  
## <a name="usingend-using-construction"></a>Usar... End using  
 La `Using...End Using` construcción establece un bloque de instrucciones en el que se usa un recurso como una conexión SQL. Opcionalmente, puede adquirir el recurso con la `Using` instrucción. Al salir del `Using` bloque, Visual Basic desecha automáticamente el recurso para que esté disponible para que lo use otro código. El recurso debe ser local y descartable. Para obtener más información, vea [using (instrucción](../../../language-reference/statements/using-statement.md)).  
  
## <a name="withend-with-construction"></a>Con... End with (construcción)  
 La `With...End With` construcción permite especificar una sola referencia de objeto y, a continuación, ejecutar una serie de instrucciones que tienen acceso a sus miembros. Esto puede simplificar el código y mejorar el rendimiento, ya que Visual Basic no tiene que volver a establecer la referencia para cada instrucción que tiene acceso a ella. Para obtener más información, vea [con... End with](../../../language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>Consulte también

- [Flujo de control](index.md)
- [Estructuras de decisión](decision-structures.md)
- [Estructuras de bucle](loop-structures.md)
- [Estructuras de control anidadas](nested-control-structures.md)
- [Using (instrucción)](../../../language-reference/statements/using-statement.md)
- [Instrucción With...End With](../../../language-reference/statements/with-end-with-statement.md)
