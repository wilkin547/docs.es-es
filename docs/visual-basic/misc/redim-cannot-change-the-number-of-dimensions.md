---
title: "'ReDim' no puede cambiar el número de dimensiones."
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: fb60c93f988ca40305f13cca07f55a70bd779081
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664400"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a>'ReDim' no puede cambiar el número de dimensiones.
Una operación intenta usar la instrucción `ReDim` para cambiar el rango (número de dimensiones) de una matriz. `ReDim` puede cambiar el tamaño de una o más dimensiones de una matriz que ya se ha declarado formalmente, pero no puede cambiar el rango de la matriz.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Asegúrese de que intenta cambiar el rango de la matriz y no los tamaños de sus dimensiones y, si es posible, use `Dim` para declarar una nueva matriz con el rango deseado.  
  
## <a name="see-also"></a>Vea también

- [Matrices en Visual Basic](../programming-guide/language-features/arrays/index.md)
- [Dimensiones de matriz en Visual Basic](../programming-guide/language-features/arrays/array-dimensions.md)
- [ReDim (instrucción)](../../visual-basic/language-reference/statements/redim-statement.md)
- [Dim (instrucción)](../../visual-basic/language-reference/statements/dim-statement.md)
