---
title: 'Procedimiento Utilizar un diccionario para almacenar instancias de eventos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: f3b8e313bd0b1bd3973102caebb9bbc9da620ae6
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203037"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="4e1c3-102">Procedimiento Utilizar un diccionario para almacenar instancias de eventos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="4e1c3-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="4e1c3-103">Uno de los usos de `accessor-declarations` consiste en exponer numerosos eventos sin asignar un campo a cada evento, pero usando en su lugar un diccionario para almacenar las instancias del evento.</span><span class="sxs-lookup"><span data-stu-id="4e1c3-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="4e1c3-104">Esto solo es útil si tiene muchos eventos, pero espera que la mayoría de ellos no se implemente.</span><span class="sxs-lookup"><span data-stu-id="4e1c3-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e1c3-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e1c3-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="4e1c3-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e1c3-106">See also</span></span>

- [<span data-ttu-id="4e1c3-107">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4e1c3-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4e1c3-108">Eventos</span><span class="sxs-lookup"><span data-stu-id="4e1c3-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="4e1c3-109">Delegados</span><span class="sxs-lookup"><span data-stu-id="4e1c3-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
