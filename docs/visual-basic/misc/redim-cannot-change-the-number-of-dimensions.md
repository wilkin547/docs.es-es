---
title: '&#39;ReDim&#39; no se puede cambiar el número de dimensiones'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: bfd4096141833b85a2126340ef549e1e1d1f8e3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="39redim39-cannot-change-the-number-of-dimensions"></a>&#39;ReDim&#39; no se puede cambiar el número de dimensiones
Una operación intenta usar la instrucción `ReDim` para cambiar el rango (número de dimensiones) de una matriz. `ReDim` puede cambiar el tamaño de una o más dimensiones de una matriz que ya se ha declarado formalmente, pero no puede cambiar el rango de la matriz.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asegúrese de que intenta cambiar el rango de la matriz y no los tamaños de sus dimensiones y, si es posible, use `Dim` para declarar una nueva matriz con el rango deseado.  
  
## <a name="see-also"></a>Vea también  
 [Matrices en Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [Dimensiones de la matriz en Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [ReDim (instrucción)](../../visual-basic/language-reference/statements/redim-statement.md)  
 [Dim (instrucción)](../../visual-basic/language-reference/statements/dim-statement.md)
