---
title: "Esta matriz es fija o está bloqueada temporalmente (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: adff10d4ae61e45402df64ebaa3baf146371ff9e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
