---
title: El objeto o la clase no admite el conjunto de eventos
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be4b9140222ef969bfb836fd74f45b8f662360b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="bcbb8-102">El objeto o la clase no admite el conjunto de eventos</span><span class="sxs-lookup"><span data-stu-id="bcbb8-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="bcbb8-103">Se intentó usar un `WithEvents` variable con un componente que no puede funcionar como un origen de eventos para el conjunto de eventos especificado.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="bcbb8-104">Por ejemplo, desea recibir los eventos de un objeto, a continuación, cree otro objeto que `Implements` el primer objeto.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="bcbb8-105">Aunque podría pensar que podría recibir los eventos del objeto implementado, esto no es siempre el caso.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="bcbb8-106">`Implements`sólo implementa una interfaz para los métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="bcbb8-107">`WithEvents`no se admite para privada `UserControls`, porque el tipo de información necesaria para generar el `ObjectEvent` no está disponible en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bcbb8-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="bcbb8-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="bcbb8-109">No puede recibir eventos para un componente que no del origen de eventos.</span><span class="sxs-lookup"><span data-stu-id="bcbb8-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcbb8-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcbb8-110">See Also</span></span>  
 [<span data-ttu-id="bcbb8-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="bcbb8-111">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [<span data-ttu-id="bcbb8-112">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bcbb8-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
