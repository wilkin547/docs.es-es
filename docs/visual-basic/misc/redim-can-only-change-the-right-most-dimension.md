---
title: "'ReDim' solo puede cambiar la dimensión situada más a la derecha"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: c3a18bb93d1253628d73919b18fe4614d742d280
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077389"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a>'ReDim' solo puede cambiar la dimensión situada más a la derecha

Una instrucción `ReDim` intentó usar la palabra clave `Preserve` para cambiar una dimensión de una matriz que no es la última dimensión. Si usa `Preserve`, solo puede cambiar el tamaño de la última dimensión de la matriz. Para todas las demás dimensiones, debe especificar el mismo tamaño que la matriz existente.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Quite la palabra clave `Preserve` .  
  
## <a name="see-also"></a>Vea también

- [Matrices en Visual Basic](../programming-guide/language-features/arrays/index.md)
- [Dimensiones de matriz en Visual Basic](../programming-guide/language-features/arrays/array-dimensions.md)
- [Instrucción ReDim](../language-reference/statements/redim-statement.md)
- [Instrucción Dim](../language-reference/statements/dim-statement.md)
