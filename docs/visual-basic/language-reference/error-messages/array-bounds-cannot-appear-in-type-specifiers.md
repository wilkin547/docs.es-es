---
title: Los límites de matriz no pueden aparecer en los especificadores de tipo
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 770f86ca960110965b6917a22d284678ff8b6f8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a>Los límites de matriz no pueden aparecer en los especificadores de tipo
Los tamaños de matriz no pueden declararse como parte de un especificador de tipo de datos.  
  
 **Id. de error:** BC30638  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Especifique el tamaño de la matriz inmediatamente después del nombre de variable en lugar de establecer el tamaño de matriz detrás del tipo, como se muestra en el ejemplo siguiente.  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   Definir una matriz e inicialícela con el número deseado de elementos, como se muestra en el ejemplo siguiente.  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)
