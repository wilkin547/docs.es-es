---
title: '&#39;&lt;MethodName&gt; &#39; tiene varias definiciones con firmas idénticas'
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 059d152cf9c3fae77ab53a4a9248b36d99614c8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593735"
---
# <a name="39ltmethodnamegt39-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="fd5b1-102">&#39;&lt;MethodName&gt; &#39; tiene varias definiciones con firmas idénticas</span><span class="sxs-lookup"><span data-stu-id="fd5b1-102">&#39;&lt;methodname&gt;&#39; has multiple definitions with identical signatures</span></span>
<span data-ttu-id="fd5b1-103">A `Function` o `Sub` declaración de procedimiento usa el procedimiento idéntico nombre y lista de argumentos que una declaración anterior.</span><span class="sxs-lookup"><span data-stu-id="fd5b1-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="fd5b1-104">Una posible causa es un intento de sobrecargar el procedimiento original.</span><span class="sxs-lookup"><span data-stu-id="fd5b1-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="fd5b1-105">Los procedimientos sobrecargados deben tener distintas listas de argumentos.</span><span class="sxs-lookup"><span data-stu-id="fd5b1-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="fd5b1-106">**Id. de error:** BC30269</span><span class="sxs-lookup"><span data-stu-id="fd5b1-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fd5b1-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="fd5b1-107">To correct this error</span></span>  
  
-   <span data-ttu-id="fd5b1-108">Cambiar el nombre del procedimiento o la lista de argumentos, o quite la declaración duplicada.</span><span class="sxs-lookup"><span data-stu-id="fd5b1-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd5b1-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd5b1-109">See Also</span></span>  
 [<span data-ttu-id="fd5b1-110">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="fd5b1-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="fd5b1-111">Consideraciones sobre la sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="fd5b1-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
