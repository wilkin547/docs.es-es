---
title: '&lt;tipo1&gt;&#39;&lt;typename&gt; &#39; debe implementar &#39; &lt;methodname&gt; &#39; para la interfaz de &#39; &lt;interfacename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: daeeab853f6a7f582542fa15ffc09ce749731d6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594388"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a><span data-ttu-id="2d52b-102">&lt;tipo1&gt;&#39;&lt;typename&gt; &#39; debe implementar &#39; &lt;methodname&gt; &#39; para la interfaz de &#39; &lt;interfacename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="2d52b-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;methodname&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;</span></span>
<span data-ttu-id="2d52b-103">Una clase o estructura intenta implementar una interfaz, pero no implementa un procedimiento definido por la interfaz.</span><span class="sxs-lookup"><span data-stu-id="2d52b-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="2d52b-104">Se deben implementar todos los miembros de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="2d52b-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="2d52b-105">**Id. de error:** BC30149</span><span class="sxs-lookup"><span data-stu-id="2d52b-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2d52b-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2d52b-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="2d52b-107">Declare un procedimiento con el mismo nombre y firma, tal como se define en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="2d52b-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="2d52b-108">No olvide incluir al menos la `End Function` o `End Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="2d52b-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="2d52b-109">Agregar un `Implements` cláusula al final de la `Function` o `Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="2d52b-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="2d52b-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2d52b-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2d52b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d52b-111">See Also</span></span>  
 [<span data-ttu-id="2d52b-112">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2d52b-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="2d52b-113">Interfaces</span><span class="sxs-lookup"><span data-stu-id="2d52b-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
