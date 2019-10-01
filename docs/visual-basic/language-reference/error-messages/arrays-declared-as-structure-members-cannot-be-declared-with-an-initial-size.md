---
title: Las matrices declaradas como miembros de estructura no se pueden declarar con un tamaño inicial
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: de9d77aa9ea853b6f044e91878044115588ca77c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701246"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="0ec33-102">Las matrices declaradas como miembros de estructura no se pueden declarar con un tamaño inicial</span><span class="sxs-lookup"><span data-stu-id="0ec33-102">Arrays declared as structure members cannot be declared with an initial size</span></span>
<span data-ttu-id="0ec33-103">Una matriz de una estructura se declara con un tamaño inicial.</span><span class="sxs-lookup"><span data-stu-id="0ec33-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="0ec33-104">No se puede inicializar ningún elemento de estructura y declarar un tamaño de matriz es una forma de inicialización.</span><span class="sxs-lookup"><span data-stu-id="0ec33-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>  
  
 <span data-ttu-id="0ec33-105">**IDENTIFICADOR de error:** BC31043</span><span class="sxs-lookup"><span data-stu-id="0ec33-105">**Error ID:** BC31043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0ec33-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="0ec33-106">To correct this error</span></span>  
  
1. <span data-ttu-id="0ec33-107">Defina la matriz en la estructura como dinámica (sin tamaño inicial).</span><span class="sxs-lookup"><span data-stu-id="0ec33-107">Define the array in your structure as dynamic (no initial size).</span></span>  
  
2. <span data-ttu-id="0ec33-108">Si necesita un determinado tamaño de matriz, puede redimensionar una matriz dinámica con una [instrucción ReDim](../../../visual-basic/language-reference/statements/redim-statement.md) cuando se esté ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="0ec33-108">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="0ec33-109">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0ec33-109">The following example illustrates this.</span></span>  
  
    ```vb  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0ec33-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ec33-110">See also</span></span>

- [<span data-ttu-id="0ec33-111">Matrices</span><span class="sxs-lookup"><span data-stu-id="0ec33-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="0ec33-112">Cómo: Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="0ec33-112">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
