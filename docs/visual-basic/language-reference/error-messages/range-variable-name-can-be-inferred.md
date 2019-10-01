---
title: El nombre de una variable de rango sólo se puede inferir a partir de un nombre simple o completo sin argumentos
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: f448f34dc5909b9128fc700abab5b4f00e911edf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701011"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="5e7ad-102">El nombre de una variable de rango sólo se puede inferir a partir de un nombre simple o completo sin argumentos</span><span class="sxs-lookup"><span data-stu-id="5e7ad-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="5e7ad-103">Un elemento de programación que toma uno o más argumentos se incluye en una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="5e7ad-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="5e7ad-104">El compilador no puede inferir una variable de rango de ese elemento de programación.</span><span class="sxs-lookup"><span data-stu-id="5e7ad-104">The compiler is unable to infer a range variable from that programming element.</span></span>  
  
 <span data-ttu-id="5e7ad-105">**IDENTIFICADOR de error:** BC36599</span><span class="sxs-lookup"><span data-stu-id="5e7ad-105">**Error ID:** BC36599</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5e7ad-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5e7ad-106">To correct this error</span></span>  
  
1. <span data-ttu-id="5e7ad-107">Proporcione un nombre de variable explícito para el elemento de programación, tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e7ad-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>  
  
```vb  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e7ad-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e7ad-108">See also</span></span>

- [<span data-ttu-id="5e7ad-109">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5e7ad-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="5e7ad-110">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="5e7ad-110">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
