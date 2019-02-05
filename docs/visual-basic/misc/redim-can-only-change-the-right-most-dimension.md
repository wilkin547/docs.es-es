---
title: "'ReDim' solo puede cambiar la dimensión situada más a la derecha"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: d20d0374cd5183b6216d1c6e5b138256cf0a4f17
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738960"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a>'ReDim' solo puede cambiar la dimensión situada más a la derecha
Una instrucción `ReDim` intentó usar la palabra clave `Preserve` para cambiar una dimensión de una matriz que no es la última dimensión. Si usa `Preserve`, solo puede cambiar el tamaño de la última dimensión de la matriz. Para todas las demás dimensiones, debe especificar el mismo tamaño que la matriz existente.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Quite la palabra clave `Preserve` .  
  
## <a name="see-also"></a>Vea también
- [Matrices en Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [Dimensiones de la matriz en Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [ReDim (instrucción)](../../visual-basic/language-reference/statements/redim-statement.md)
- [Dim (instrucción)](../../visual-basic/language-reference/statements/dim-statement.md)
