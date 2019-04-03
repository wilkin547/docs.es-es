---
title: Una matriz declarada como variable de control de bucle no se puede declarar con un tamaño inicial
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: bee3bcd3701945f5cf77f6761defc8be77acf49f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843583"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="8e247-102">Una matriz declarada como variable de control de bucle no se puede declarar con un tamaño inicial</span><span class="sxs-lookup"><span data-stu-id="8e247-102">Array declared as for loop control variable cannot be declared with an initial size</span></span>
<span data-ttu-id="8e247-103">Un `For Each` bucle utiliza una matriz como su *elemento* variable de iteración, pero inicializa esa matriz.</span><span class="sxs-lookup"><span data-stu-id="8e247-103">A `For Each` loop uses an array as its *element* iteration variable but initializes that array.</span></span>  
  
 <span data-ttu-id="8e247-104">Las instrucciones siguientes muestran cómo se puede generar este error.</span><span class="sxs-lookup"><span data-stu-id="8e247-104">The following statements show how this error can be generated.</span></span>  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 <span data-ttu-id="8e247-105">La primera `For Each` instrucción es la manera correcta de tener acceso a elementos de `arrayList`.</span><span class="sxs-lookup"><span data-stu-id="8e247-105">The first `For Each` statement is the correct way to access elements of `arrayList`.</span></span> <span data-ttu-id="8e247-106">El segundo `For Each` instrucción genera este error.</span><span class="sxs-lookup"><span data-stu-id="8e247-106">The second `For Each` statement generates this error.</span></span>  
  
 <span data-ttu-id="8e247-107">**Identificador de error:** BC32039</span><span class="sxs-lookup"><span data-stu-id="8e247-107">**Error ID:** BC32039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8e247-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="8e247-108">To correct this error</span></span>  
  
-   <span data-ttu-id="8e247-109">Quite la inicialización de la declaración de la *elemento* variable de iteración.</span><span class="sxs-lookup"><span data-stu-id="8e247-109">Remove the initialization from the declaration of the *element* iteration variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e247-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e247-110">See also</span></span>

- [<span data-ttu-id="8e247-111">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8e247-111">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="8e247-112">Matrices</span><span class="sxs-lookup"><span data-stu-id="8e247-112">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="8e247-113">Colecciones</span><span class="sxs-lookup"><span data-stu-id="8e247-113">Collections</span></span>](../../../standard/collections/index.md)
