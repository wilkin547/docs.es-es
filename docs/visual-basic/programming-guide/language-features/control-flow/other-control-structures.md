---
title: Estructuras de control adicionales (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 09e59d25b3b2fc89026295e8500c30dad7b75086
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="other-control-structures-visual-basic"></a>Estructuras de control adicionales (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]proporciona estructuras de control que le ayudarán a deshacerse de un recurso o reducen el número de veces que tiene que repetir una referencia de objeto.  
  
## <a name="usingend-using-construction"></a>Uso de... Finalizar utilizando una construcción  
 El `Using...End Using` construcción establece un bloque de instrucciones dentro del cual el uso de un recurso como una conexión de SQL. Opcionalmente, puede adquirir el recurso con el `Using` instrucción. Al salir del `Using` bloque, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] elimina automáticamente el recurso para que esté disponible para otro código. El recurso debe ser local y descartable. Para obtener más información, vea [Using (Instrucción)](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>Con... Finalizar con la construcción  
 El `With...End With` construcción le permite especificar una referencia de objeto una vez y, a continuación, ejecutar una serie de instrucciones que tienen acceso a sus miembros. Esto puede simplificar el código y mejorar el rendimiento porque [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no tiene que volver a establecer la referencia para cada instrucción que tiene acceso a él. Para obtener más información, consulte [con... Terminar con la instrucción](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>Vea también  
 [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Estructuras de decisión](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Estructuras de control anidadas](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Using (instrucción)](../../../../visual-basic/language-reference/statements/using-statement.md)  
 [With...End With (instrucción)](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
