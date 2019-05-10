---
title: Los límites de matriz no pueden aparecer en los especificadores de tipo
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: 50e1cd0e41da467a9e816c8e5d64d09a36923d65
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665746"
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
