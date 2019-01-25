---
title: '&lt;tipo1&gt;&#39;&lt;typename&gt; &#39; debe implementar &#39; &lt;methodname&gt; &#39; para la interfaz &#39; &lt;interfacename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: ff9ffd50f7f21814d5e4c23fd8df50b12bf746f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642452"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a><span data-ttu-id="b9825-102">&lt;tipo1&gt;&#39;&lt;typename&gt; &#39; debe implementar &#39; &lt;methodname&gt; &#39; para la interfaz &#39; &lt;interfacename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="b9825-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;methodname&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;</span></span>
<span data-ttu-id="b9825-103">Una clase o estructura intenta implementar una interfaz, pero no implementa un procedimiento definido por la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b9825-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="b9825-104">Se deben implementar todos los miembros de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b9825-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="b9825-105">**Identificador de error:** BC30149</span><span class="sxs-lookup"><span data-stu-id="b9825-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b9825-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b9825-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="b9825-107">Declare un procedimiento con el mismo nombre y firma, tal como se define en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b9825-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="b9825-108">No olvide incluir al menos el `End Function` o `End Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b9825-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="b9825-109">Agregar un `Implements` cláusula al final de la `Function` o `Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b9825-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="b9825-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b9825-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b9825-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9825-111">See also</span></span>
- [<span data-ttu-id="b9825-112">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b9825-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="b9825-113">Interfaces</span><span class="sxs-lookup"><span data-stu-id="b9825-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
