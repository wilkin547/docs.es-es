---
description: 'Más información acerca de: esta matriz es fija o está bloqueada temporalmente (Visual Basic)'
title: Matriz fija o bloqueada temporalmente
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 034bcc23055f7fb3f707e1105589a4526e6f9009
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641218"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a>Esta matriz es fija o está bloqueada temporalmente (Visual Basic)

Este error tiene las siguientes causas posibles:  
  
- Usar `ReDim` para cambiar el número de elementos de una matriz de tamaño fijo.  
  
- Redimensionar una matriz dinámica de nivel de módulo, en la que se ha pasado un elemento como argumento a un procedimiento. Si se pasa un elemento, la matriz está bloqueada para evitar la desasignación de memoria para el parámetro de referencia dentro del procedimiento.  
  
- Se está intentando asignar un valor a una `Variant` variable que contiene una matriz, pero `Variant` está bloqueado actualmente.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Haga que la matriz original sea dinámica en lugar de fija declarándola con `ReDim` (si la matriz se declara dentro de un procedimiento) o declarándolo sin especificar el número de elementos (si la matriz se declara en el nivel de módulo).  
  
2. Determine si realmente necesita pasar el elemento, ya que es visible en todos los procedimientos del módulo.  
  
3. Determine qué está bloqueando `Variant` y soluciónelo.  
  
## <a name="see-also"></a>Vea también

- [Matrices](../../programming-guide/language-features/arrays/index.md)
