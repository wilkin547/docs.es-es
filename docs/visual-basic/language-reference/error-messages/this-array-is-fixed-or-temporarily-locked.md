---
title: Matriz fija o bloqueada temporalmente
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 8d5e4add2d92a575126fb934ac3874a2e37685f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350785"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a>Esta matriz es fija o está bloqueada temporalmente (Visual Basic)
Este error tiene las siguientes causas posibles:  
  
- Usar `ReDim` para cambiar el número de elementos de una matriz de tamaño fijo.  
  
- Redimensionar una matriz dinámica de nivel de módulo, en la que se ha pasado un elemento como argumento a un procedimiento. Si se pasa un elemento, la matriz está bloqueada para evitar la desasignación de memoria para el parámetro de referencia dentro del procedimiento.  
  
- Se intentó asignar un valor a una variable `Variant` que contiene una matriz, pero el `Variant` está bloqueado actualmente.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Haga que la matriz original sea dinámica en lugar de fija declarándola con `ReDim` (si la matriz se declara dentro de un procedimiento) o declarándolo sin especificar el número de elementos (si la matriz se declara en el nivel de módulo).  
  
2. Determine si realmente necesita pasar el elemento, ya que es visible en todos los procedimientos del módulo.  
  
3. Determine qué está bloqueando el `Variant` y Remedy.  
  
## <a name="see-also"></a>Vea también

- [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)
