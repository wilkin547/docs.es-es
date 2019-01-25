---
title: '&#39;#Region&#39; y &#39;#End Region&#39; instrucciones no son válidas dentro la lambda de varias líneas cuerpos de método'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 55399cd123ce4d67cc833f2eabe3230acdafc0bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737220"
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>&#39;#Region&#39; y &#39;#End Region&#39; las instrucciones no son válidas dentro de lambdas de varias líneas/cuerpos de método
El `#Region` bloque debe declararse en un nivel de clase, módulo o espacio de nombres. Una región contraíble puede incluir uno o varios procedimientos, pero no puede comenzar ni terminar dentro de un procedimiento.  
  
 **Identificador de error:** BC32025  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que el procedimiento anterior esté terminado correctamente con un `End Function` o `End Sub` instrucción.  
  
2.  Asegúrese de que el `#Region` y `#End Region` las directivas tienen el mismo bloque de código.  
  
## <a name="see-also"></a>Vea también
- [#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md)
