---
title: Las instrucciones '#Region' y '#End Region' no son válidas dentro de lambda de varias líneas cuerpos de método
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: deef3de645040d7c3d95b1a6c8a25fcf10de881b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842712"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>Las instrucciones '#Region' y '#End Region' no son válidas en los cuerpos de método y operaciones lambda de varias líneas
El `#Region` bloque debe declararse en un nivel de clase, módulo o espacio de nombres. Una región contraíble puede incluir uno o varios procedimientos, pero no puede comenzar ni terminar dentro de un procedimiento.  
  
 **Identificador de error:** BC32025  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que el procedimiento anterior esté terminado correctamente con un `End Function` o `End Sub` instrucción.  
  
2.  Asegúrese de que el `#Region` y `#End Region` las directivas tienen el mismo bloque de código.  
  
## <a name="see-also"></a>Vea también

- [#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md)
