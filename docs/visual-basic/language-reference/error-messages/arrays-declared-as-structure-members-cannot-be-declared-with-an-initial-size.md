---
title: Las matrices declaradas como miembros de estructura no se pueden declarar con un tamaño inicial
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 58889809b3d8d0823784279c421a141dc8056984
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841971"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>Las matrices declaradas como miembros de estructura no se pueden declarar con un tamaño inicial
Una matriz en una estructura se declara con un tamaño inicial. No se puede inicializar cualquier elemento de estructura y declarar un tamaño de matriz es una forma de inicialización.  
  
 **Identificador de error:** BC31043  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Definir la matriz en la estructura como dinámico (ningún tamaño inicial).  
  
2.  Si necesita un determinado tamaño de matriz, puede redimensionar una matriz dinámica con un [instrucción ReDim](../../../visual-basic/language-reference/statements/redim-statement.md) cuando se ejecuta el código. Esto se ilustra en el siguiente ejemplo:  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vea también

- [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Cómo: Declarar una estructura](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
