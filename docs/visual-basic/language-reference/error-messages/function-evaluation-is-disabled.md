---
title: "Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anterior"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords: BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 05067e730486b443b7a508adb499f34c060d5093
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anterior
Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anterior Para volver a habilitar la evaluación de funciones, vuelva a intentarlo o reinicie la depuración.  
  
 En el depurador de Visual Studio, una expresión especifica una llamada a procedimiento, pero otra evaluación ha agotado de tiempo de espera.  
  
 Posibles causas de una llamada de procedimiento a tiempo de espera incluyen un bucle infinito o *bucle sin fin*. Para obtener más información, vea [para... Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 Es un caso especial de un bucle infinito *recursividad*. Para obtener más información, consulte [procedimientos recursivos](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **Id. de error:** BC30957  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Si es posible, determine cuál era la evaluación de función anterior y lo que lo produjo que se superara el tiempo de espera. De lo contrario, podría encontrar de nuevo este error.  
  
2.  O bien, ejecute paso a paso de nuevo el depurador, o finalice y reinicie la depuración.  
  
## <a name="see-also"></a>Vea también  
 [Depurar en Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)  
 [Desplazarse por el código con el depurador](/visualstudio/debugger/navigating-through-code-with-the-debugger)
