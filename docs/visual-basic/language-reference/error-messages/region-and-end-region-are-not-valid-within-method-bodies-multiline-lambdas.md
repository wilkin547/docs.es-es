---
title: "&#39; #Region &#39; y &#39; #End Region &#39; las instrucciones no son válidas dentro de expresiones lambda de multilínea de cuerpos de método"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 614d0c7324bfbf07bc5736c799e8b54937ead081
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>&#39; #Region &#39; y &#39; #End Region &#39; las instrucciones no son válidas dentro de expresiones lambda de varias líneas/cuerpos de método
El `#Region` bloque debe declararse en un nivel de clase, módulo o espacio de nombres. Una región contraíble puede incluir uno o varios procedimientos, pero no puede comenzar ni terminar dentro de un procedimiento.  
  
 **Id. de error:** BC32025  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que el procedimiento anterior esté terminado correctamente con un `End Function` o `End Sub` instrucción.  
  
2.  Asegúrese de que el `#Region` y `#End Region` directivas están en el mismo bloque de código.  
  
## <a name="see-also"></a>Vea también  
 [#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md)
