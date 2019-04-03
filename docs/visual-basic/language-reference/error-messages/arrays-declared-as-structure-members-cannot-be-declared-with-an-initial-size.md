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
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="a5093-102">Las matrices declaradas como miembros de estructura no se pueden declarar con un tamaño inicial</span><span class="sxs-lookup"><span data-stu-id="a5093-102">Arrays declared as structure members cannot be declared with an initial size</span></span>
<span data-ttu-id="a5093-103">Una matriz en una estructura se declara con un tamaño inicial.</span><span class="sxs-lookup"><span data-stu-id="a5093-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="a5093-104">No se puede inicializar cualquier elemento de estructura y declarar un tamaño de matriz es una forma de inicialización.</span><span class="sxs-lookup"><span data-stu-id="a5093-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>  
  
 <span data-ttu-id="a5093-105">**Identificador de error:** BC31043</span><span class="sxs-lookup"><span data-stu-id="a5093-105">**Error ID:** BC31043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a5093-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a5093-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="a5093-107">Definir la matriz en la estructura como dinámico (ningún tamaño inicial).</span><span class="sxs-lookup"><span data-stu-id="a5093-107">Define the array in your structure as dynamic (no initial size).</span></span>  
  
2.  <span data-ttu-id="a5093-108">Si necesita un determinado tamaño de matriz, puede redimensionar una matriz dinámica con un [instrucción ReDim](../../../visual-basic/language-reference/statements/redim-statement.md) cuando se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="a5093-108">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="a5093-109">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a5093-109">The following example illustrates this.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a5093-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5093-110">See also</span></span>

- [<span data-ttu-id="a5093-111">Matrices</span><span class="sxs-lookup"><span data-stu-id="a5093-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="a5093-112">Cómo: Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="a5093-112">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
