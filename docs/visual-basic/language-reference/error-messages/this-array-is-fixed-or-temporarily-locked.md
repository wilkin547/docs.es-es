---
title: Esta matriz es fija o está bloqueada temporalmente (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: e912bd202603d9a0f427418708ad584c7d6203e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593569"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a>Esta matriz es fija o está bloqueada temporalmente (Visual Basic)
Este error tiene las siguientes causas posibles:  
  
-   Usar `ReDim` para cambiar el número de elementos de una matriz de tamaño fijo.  
  
-   Cambiar el tamaño de una matriz dinámica de nivel de módulo, en el que se ha pasado un elemento como un argumento a un procedimiento. Si se pasa un elemento, la matriz está bloqueada para evitar la desasignación de memoria para el parámetro de referencia dentro del procedimiento.  
  
-   Intenta asignar un valor a un `Variant` variable que contiene una matriz, pero la `Variant` está bloqueado actualmente.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Hacer que la matriz original dinámica en lugar de fija declarándola con `ReDim` (si la matriz se declara dentro de un procedimiento), o mediante la declaración sin especificar el número de elementos (si la matriz se declara en el nivel de módulo.  
  
2.  Determine si realmente necesita pasar el elemento, ya que es visible dentro de todos los procedimientos en el módulo.  
  
3.  Determinar la causa del bloqueo del `Variant` y soluciónelo.  
  
## <a name="see-also"></a>Vea también  
 [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)
