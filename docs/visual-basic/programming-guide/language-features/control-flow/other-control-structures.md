---
title: Otras estructuras de Control (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 639571b493037f26951bd8fbf140d7bce3244889
ms.lasthandoff: 03/13/2017

---
# <a name="other-control-structures-visual-basic"></a>Estructuras de control adicionales (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]proporciona estructuras de control que le ayudarán a deshacerse de un recurso o reducen el número de veces que tiene que repetir una referencia de objeto.  
  
## <a name="usingend-using-construction"></a>Uso de... Extremo utilizando una construcción  
 El `Using...End Using` construcción establece un bloque de instrucciones dentro del cual el uso de un recurso como una conexión SQL. Opcionalmente, puede adquirir el recurso con el `Using` instrucción. Al salir del `Using` bloque, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] elimina automáticamente el recurso para que esté disponible para otro código. El recurso debe ser local y descartable. Para obtener más información, consulte [instrucción Using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>Con... Termina con la construcción  
 El `With...End With` le permite especificar una referencia de objeto una vez y, a continuación, ejecutar una serie de instrucciones que tienen acceso a sus miembros. Esto puede simplificar su código y mejorar el rendimiento porque [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no tiene que volver a establecer la referencia para cada instrucción que tiene acceso a él. Para obtener más información, consulte [con... Terminar con la instrucción](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>Vea también  
 [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Estructuras de decisión](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Estructuras de Control anidadas](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Instrucción using](../../../../visual-basic/language-reference/statements/using-statement.md)   
 [With...End With (instrucción)](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
