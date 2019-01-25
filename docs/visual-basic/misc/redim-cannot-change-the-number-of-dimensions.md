---
title: "'ReDim' no puede cambiar el número de dimensiones."
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 80546b427afdafaf6e9fcea493d58cf1019e79e9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638462"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a>'ReDim' no puede cambiar el número de dimensiones.
Una operación intenta usar la instrucción `ReDim` para cambiar el rango (número de dimensiones) de una matriz. `ReDim` puede cambiar el tamaño de una o más dimensiones de una matriz que ya se ha declarado formalmente, pero no puede cambiar el rango de la matriz.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asegúrese de que intenta cambiar el rango de la matriz y no los tamaños de sus dimensiones y, si es posible, use `Dim` para declarar una nueva matriz con el rango deseado.  
  
## <a name="see-also"></a>Vea también
- [Matrices en Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [Dimensiones de la matriz en Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [ReDim (instrucción)](../../visual-basic/language-reference/statements/redim-statement.md)
- [Dim (instrucción)](../../visual-basic/language-reference/statements/dim-statement.md)
