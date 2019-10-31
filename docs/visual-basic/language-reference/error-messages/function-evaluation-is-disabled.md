---
title: Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anterior
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: d004c89b742944622ce45e6a2be8d96116252745
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197564"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anterior
La evaluación de la función está deshabilitada porque se agotó el tiempo de espera de evaluación de la función anterior. Para volver a habilitar la evaluación de funciones, vuelva a ejecutar el paso o reinicie la depuración.  
  
 En el depurador de Visual Studio, una expresión especifica una llamada a procedimiento, pero otra evaluación ha agotado de tiempo de espera.  
  
 Las posibles causas de que se agote el tiempo de espera de una llamada a un procedimiento incluyen un bucle infinito o un *bucle sin fin*. Para obtener más información, vea [para... Instrucción siguiente](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 Un caso especial de un bucle infinito es la *recursividad*. Para obtener más información, vea [procedimientos recursivos](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **Identificador de error:** BC30957  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Si es posible, Determine cuál era la evaluación de la función anterior y qué hizo que se agotara el tiempo de espera. De lo contrario, es posible que se produzca este error de nuevo.  
  
2. O bien, ejecute paso a paso de nuevo el depurador, o finalice y reinicie la depuración.  
  
## <a name="see-also"></a>Vea también

- [Depurar en Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Desplazarse por el código con el depurador](/visualstudio/debugger/navigating-through-code-with-the-debugger)
