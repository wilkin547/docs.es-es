---
title: "'ReDim' no puede cambiar el número de dimensiones."
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 8d80af7682f27b403e0f463fdbebbcac71f18b01
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077376"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a>'ReDim' no puede cambiar el número de dimensiones.

Una operación intenta usar la instrucción `ReDim` para cambiar el rango (número de dimensiones) de una matriz. `ReDim` puede cambiar el tamaño de una o más dimensiones de una matriz que ya se ha declarado formalmente, pero no puede cambiar el rango de la matriz.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Asegúrese de que intenta cambiar el rango de la matriz y no los tamaños de sus dimensiones y, si es posible, use `Dim` para declarar una nueva matriz con el rango deseado.  
  
## <a name="see-also"></a>Vea también

- [Matrices en Visual Basic](../programming-guide/language-features/arrays/index.md)
- [Dimensiones de matriz en Visual Basic](../programming-guide/language-features/arrays/array-dimensions.md)
- [Instrucción ReDim](../language-reference/statements/redim-statement.md)
- [Instrucción Dim](../language-reference/statements/dim-statement.md)
