---
title: Los límites de matriz no pueden aparecer en los especificadores de tipo
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: 45787db51de562f2266c587fd2bb15ef29ebefbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583688"
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
