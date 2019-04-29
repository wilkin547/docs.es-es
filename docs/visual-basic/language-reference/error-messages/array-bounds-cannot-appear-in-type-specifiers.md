---
title: Los límites de matriz no pueden aparecer en los especificadores de tipo
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: f20ed883005641082eb89e2effa5221594910ffe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935361"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a>Los límites de matriz no pueden aparecer en los especificadores de tipo
Los tamaños de matriz no pueden declararse como parte de un especificador de tipo de datos.  
  
 **Identificador de error:** BC30638  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Especifique el tamaño de la matriz inmediatamente después del nombre de variable en lugar de colocar el tamaño de matriz detrás del tipo, como se muestra en el ejemplo siguiente.  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
- Definir una matriz e inicialícela con el número deseado de elementos, como se muestra en el ejemplo siguiente.  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a>Vea también

- [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)
