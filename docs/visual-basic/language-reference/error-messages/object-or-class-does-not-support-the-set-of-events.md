---
title: El objeto o la clase no admite el conjunto de eventos
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: ad9176b5332a75f03968e742501c3fce541055de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342887"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="23dcf-102">El objeto o la clase no admite el conjunto de eventos</span><span class="sxs-lookup"><span data-stu-id="23dcf-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="23dcf-103">Se intentó usar un `WithEvents` variable con un componente que no puede funcionar como un origen de eventos para el conjunto de eventos especificado.</span><span class="sxs-lookup"><span data-stu-id="23dcf-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="23dcf-104">Por ejemplo, desea recibir los eventos de un objeto y, después, cree otro objeto que `Implements` el primer objeto.</span><span class="sxs-lookup"><span data-stu-id="23dcf-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="23dcf-105">Aunque es posible que cree que puede recibir los eventos del objeto implementado, esto no es siempre el caso.</span><span class="sxs-lookup"><span data-stu-id="23dcf-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="23dcf-106">`Implements` solo se implementa una interfaz para los métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="23dcf-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="23dcf-107">`WithEvents` no se admite para privada `UserControls`, porque el tipo de información necesaria para generar el `ObjectEvent` no está disponible en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="23dcf-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="23dcf-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="23dcf-108">To correct this error</span></span>  
  
1. <span data-ttu-id="23dcf-109">No puede recibir eventos para un componente que no del origen de eventos.</span><span class="sxs-lookup"><span data-stu-id="23dcf-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23dcf-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="23dcf-110">See also</span></span>

- [<span data-ttu-id="23dcf-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="23dcf-111">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
- [<span data-ttu-id="23dcf-112">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="23dcf-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
