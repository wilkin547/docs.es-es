---
title: '&lt;tipo1&gt;&#39;&lt; TypeName&gt;&#39; debe implementar &#39;&lt; MemberName&gt;&#39; para la interfaz &#39;&lt; InterfaceName&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 05e0229d0259c519d4db265c017a5040b425c79a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a><span data-ttu-id="208d5-102">&lt;tipo1&gt;&#39;&lt; TypeName&gt;&#39; debe implementar &#39;&lt; MemberName&gt;&#39; para la interfaz &#39;&lt; InterfaceName&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="208d5-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;membername&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;</span></span>
<span data-ttu-id="208d5-103">'\<typename >' debe implementar '\<nombreDeMiembro >' para la interfaz '\<interfacename >'.</span><span class="sxs-lookup"><span data-stu-id="208d5-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="208d5-104">Propiedad de implementación debe tener coincidente 'ReadOnly' o 'WriteOnly' especificadores.</span><span class="sxs-lookup"><span data-stu-id="208d5-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="208d5-105">Una clase o estructura intenta implementar una interfaz, pero no implementa un procedimiento, propiedad o evento definido por la interfaz.</span><span class="sxs-lookup"><span data-stu-id="208d5-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="208d5-106">Se deben implementar todos los miembros de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="208d5-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="208d5-107">**Id. de error:** BC30154</span><span class="sxs-lookup"><span data-stu-id="208d5-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="208d5-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="208d5-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="208d5-109">Declarar a un miembro con el mismo nombre y firma, tal como se define en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="208d5-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="208d5-110">No olvide incluir al menos la `End Function`, `End Sub`, o `End Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="208d5-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="208d5-111">Agregar un `Implements` cláusula al final de la `Function`, `Sub`, `Property`, o `Event` instrucción.</span><span class="sxs-lookup"><span data-stu-id="208d5-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="208d5-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="208d5-112">For example:</span></span>  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  <span data-ttu-id="208d5-113">Al implementar una propiedad, asegúrese de que `ReadOnly` o `WriteOnly` se utiliza en la misma manera que en la definición de interfaz.</span><span class="sxs-lookup"><span data-stu-id="208d5-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4.  <span data-ttu-id="208d5-114">Al implementar una propiedad, declare `Get` y `Set` procedimientos, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="208d5-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="208d5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="208d5-115">See Also</span></span>  
 [<span data-ttu-id="208d5-116">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="208d5-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="208d5-117">Interfaces</span><span class="sxs-lookup"><span data-stu-id="208d5-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
