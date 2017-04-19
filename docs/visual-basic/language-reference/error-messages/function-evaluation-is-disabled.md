---
title: "Se deshabilitó la evaluación de función porque agotó una evaluación de función anterior | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30957
- vbc30957
dev_langs:
- VB
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: b861b5c6c151c5d3aeec2810c7f2a228f22fdf6e
ms.lasthandoff: 03/13/2017

---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anterior
Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anterior Para volver a habilitar la evaluación de funciones, vuelva a intentarlo o reinicie la depuración.  
  
 En el depurador de Visual Studio, una expresión especifica una llamada a procedimiento, pero otra evaluación ha agotado de tiempo de espera.  
  
 Las causas posibles de una llamada de procedimiento al tiempo de espera incluyen un bucle infinito o *bucle sin fin*. Para obtener más información, consulte [para... Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 Un caso especial de bucle infinito es *recursividad*. Para obtener más información, consulte [procedimientos recursivos](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **Id. de error:** BC30957  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Si es posible, determine cuál era la evaluación de función anterior y lo que lo produjo que se superara el tiempo de espera. De lo contrario, podría encontrar de nuevo este error.  
  
2.  O bien, ejecute paso a paso de nuevo el depurador, o finalice y reinicie la depuración.  
  
## <a name="see-also"></a>Vea también  
 [Depurar en Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio)   
 [Desplazarse por el código con el depurador](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)
