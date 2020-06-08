---
title: 'Cómo: Provocar y utilizar eventos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET Framework], raising
- raising events
- events [.NET Framework], samples
ms.assetid: 42afade7-3a02-4f2e-868b-95845f302f8f
ms.openlocfilehash: 4d0b24b8a6f1b914745d819b90b973752e32447c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279963"
---
# <a name="how-to-raise-and-consume-events"></a><span data-ttu-id="5c7da-102">Cómo: Provocar y utilizar eventos</span><span class="sxs-lookup"><span data-stu-id="5c7da-102">How to: Raise and Consume Events</span></span>
<span data-ttu-id="5c7da-103">En los ejemplos de este tema se muestra cómo trabajar con eventos.</span><span class="sxs-lookup"><span data-stu-id="5c7da-103">The examples in this topic show how to work with events.</span></span> <span data-ttu-id="5c7da-104">Se incluyen ejemplos del delegado <xref:System.EventHandler>, el delegado <xref:System.EventHandler%601> y un delegado personalizado, para ilustrar eventos con y sin datos.</span><span class="sxs-lookup"><span data-stu-id="5c7da-104">They include examples of the <xref:System.EventHandler> delegate, the <xref:System.EventHandler%601> delegate, and a custom delegate, to illustrate events with and without data.</span></span>  
  
 <span data-ttu-id="5c7da-105">En los ejemplos se usan los conceptos descritos en el artículo [Eventos](index.md).</span><span class="sxs-lookup"><span data-stu-id="5c7da-105">The examples use concepts described in the [Events](index.md) article.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c7da-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c7da-106">Example</span></span>  
 <span data-ttu-id="5c7da-107">En el primer ejemplo se muestra cómo generar y consumir un evento que no tiene datos.</span><span class="sxs-lookup"><span data-stu-id="5c7da-107">The first example shows how to raise and consume an event that doesn't have data.</span></span> <span data-ttu-id="5c7da-108">Contiene una clase denominada `Counter` que tiene un evento denominado `ThresholdReached`.</span><span class="sxs-lookup"><span data-stu-id="5c7da-108">It contains a class named `Counter` that has an event named `ThresholdReached`.</span></span> <span data-ttu-id="5c7da-109">Este evento se genera cuando un valor de contador iguala o supera el valor de umbral.</span><span class="sxs-lookup"><span data-stu-id="5c7da-109">This event is raised when a counter value equals or exceeds a threshold value.</span></span> <span data-ttu-id="5c7da-110">El delegado <xref:System.EventHandler> está asociado al evento, porque no se proporcionan datos de evento.</span><span class="sxs-lookup"><span data-stu-id="5c7da-110">The <xref:System.EventHandler> delegate is associated with the event, because no event data is provided.</span></span>  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="5c7da-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c7da-111">Example</span></span>  
 <span data-ttu-id="5c7da-112">En el ejemplo siguiente se muestra cómo generar y consumir un evento que proporciona datos.</span><span class="sxs-lookup"><span data-stu-id="5c7da-112">The next example shows how to raise and consume an event that provides data.</span></span> <span data-ttu-id="5c7da-113">El delegado <xref:System.EventHandler%601> está asociado al evento, y se proporciona una instancia de un objeto de datos de eventos personalizados.</span><span class="sxs-lookup"><span data-stu-id="5c7da-113">The <xref:System.EventHandler%601> delegate is associated with the event, and an instance of a custom event data object is provided.</span></span>  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="5c7da-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c7da-114">Example</span></span>  
 <span data-ttu-id="5c7da-115">En el ejemplo siguiente se muestra cómo declarar un delegado para un evento.</span><span class="sxs-lookup"><span data-stu-id="5c7da-115">The next example shows how to declare a delegate for an event.</span></span> <span data-ttu-id="5c7da-116">El delegado se denomina `ThresholdReachedEventHandler`.</span><span class="sxs-lookup"><span data-stu-id="5c7da-116">The delegate is named `ThresholdReachedEventHandler`.</span></span> <span data-ttu-id="5c7da-117">Esto es simplemente una ilustración.</span><span class="sxs-lookup"><span data-stu-id="5c7da-117">This is just an illustration.</span></span> <span data-ttu-id="5c7da-118">Normalmente no es necesario declarar un delegado para un evento, porque se puede usar el delegado <xref:System.EventHandler> o <xref:System.EventHandler%601>.</span><span class="sxs-lookup"><span data-stu-id="5c7da-118">Typically, you do not have to declare a delegate for an event, because you can use either the <xref:System.EventHandler> or the <xref:System.EventHandler%601> delegate.</span></span> <span data-ttu-id="5c7da-119">Solo debe declararse un delegado en escenarios poco habituales, como cuando se facilita el uso de una clase a código heredado que no puede usar elementos genéricos.</span><span class="sxs-lookup"><span data-stu-id="5c7da-119">You should declare a delegate only in rare scenarios, such as making your class available to legacy code that cannot use generics.</span></span>  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="5c7da-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c7da-120">See also</span></span>

- [<span data-ttu-id="5c7da-121">Eventos</span><span class="sxs-lookup"><span data-stu-id="5c7da-121">Events</span></span>](index.md)
