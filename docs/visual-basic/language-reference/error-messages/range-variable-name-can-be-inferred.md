---
title: El nombre de una variable de rango sólo se puede inferir a partir de un nombre simple o completo sin argumentos
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: a0b5633bb0efb3c67f73810552ef9a14ac3d0c70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331655"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="771b2-102">El nombre de una variable de rango sólo se puede inferir a partir de un nombre simple o completo sin argumentos</span><span class="sxs-lookup"><span data-stu-id="771b2-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="771b2-103">Se incluye un elemento de programación que toma uno o más argumentos en una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="771b2-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="771b2-104">El compilador no puede inferir una variable de rango de ese elemento de programación.</span><span class="sxs-lookup"><span data-stu-id="771b2-104">The compiler is unable to infer a range variable from that programming element.</span></span>  
  
 <span data-ttu-id="771b2-105">**Identificador de error:** BC36599</span><span class="sxs-lookup"><span data-stu-id="771b2-105">**Error ID:** BC36599</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="771b2-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="771b2-106">To correct this error</span></span>  
  
1. <span data-ttu-id="771b2-107">Proporcione un nombre de variable explícito para el elemento de programación, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="771b2-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a><span data-ttu-id="771b2-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="771b2-108">See also</span></span>

- [<span data-ttu-id="771b2-109">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="771b2-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="771b2-110">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="771b2-110">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
