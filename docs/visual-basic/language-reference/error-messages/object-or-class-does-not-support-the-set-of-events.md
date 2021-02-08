---
description: 'Más información sobre: el objeto o la clase no admite el conjunto de eventos.'
title: El objeto o la clase no admite el conjunto de eventos
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: f13d47a6bb75a5e8394f5344b954afa523bedab3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795606"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="9c524-103">El objeto o la clase no admite el conjunto de eventos</span><span class="sxs-lookup"><span data-stu-id="9c524-103">Object or class does not support the set of events</span></span>

<span data-ttu-id="9c524-104">Ha intentado usar una `WithEvents` variable con un componente que no puede funcionar como un origen de eventos para el conjunto de eventos especificado.</span><span class="sxs-lookup"><span data-stu-id="9c524-104">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="9c524-105">Por ejemplo, desea recibir los eventos de un objeto y, a continuación, crear otro objeto que sea `Implements` el primer objeto.</span><span class="sxs-lookup"><span data-stu-id="9c524-105">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="9c524-106">Aunque podría pensar que podría recibir los eventos del objeto implementado, este no es siempre el caso.</span><span class="sxs-lookup"><span data-stu-id="9c524-106">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="9c524-107">`Implements` solo implementa una interfaz para los métodos y las propiedades.</span><span class="sxs-lookup"><span data-stu-id="9c524-107">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="9c524-108">`WithEvents` no se admite para Private `UserControls` , porque la información de tipo necesaria para generar `ObjectEvent` no está disponible en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9c524-108">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="9c524-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="9c524-109">To correct this error</span></span>

- <span data-ttu-id="9c524-110">No se pueden recibir eventos para un componente que no tiene eventos de origen.</span><span class="sxs-lookup"><span data-stu-id="9c524-110">You cannot sink events for a component that does not source events.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c524-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c524-111">See also</span></span>

- [<span data-ttu-id="9c524-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="9c524-112">WithEvents</span></span>](../modifiers/withevents.md)
- [<span data-ttu-id="9c524-113">Implements (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="9c524-113">Implements Statement</span></span>](../statements/implements-statement.md)
