---
description: "Más información sobre: BC31423: el evento ' <eventname1> ' no puede implementar <eventname2> el evento ' ' en la interfaz ' <interface> ' porque sus tipos delegados ' <delegate1> ' y ' <delegate2> ' no coinciden"
title: El evento '<eventname1>' no puede implementar el evento '<eventname2>' en la interfaz '<interface>' porque sus tipos delegados '<delegate1>' y '<delegate2>' no coinciden
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: cfb967d2b43ce1f34f56f3d019a9a663b000296c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796462"
---
# <a name="bc31423-event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a><span data-ttu-id="24163-103">BC31423: el evento ' \<eventname1> ' no puede implementar \<eventname2> el evento ' ' en la interfaz ' \<interface> ' porque sus tipos delegados ' \<delegate1> ' y ' \<delegate2> ' no coinciden</span><span class="sxs-lookup"><span data-stu-id="24163-103">BC31423: Event '\<eventname1>' cannot implement event '\<eventname2>' on interface '\<interface>' because their delegate types '\<delegate1>' and '\<delegate2>' do not match</span></span>

<span data-ttu-id="24163-104">Visual Basic no puede implementar un evento porque el tipo delegado del evento no coincide con el tipo delegado del evento en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="24163-104">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="24163-105">Este error puede producirse cuando define varios eventos en una interfaz e intenta implementarlos juntos con el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="24163-105">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="24163-106">Un evento puede implementar dos o más eventos solo si todos los eventos implementados se declaran con la sintaxis `As` y si se especifica el mismo tipo delegado.</span><span class="sxs-lookup"><span data-stu-id="24163-106">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>

 <span data-ttu-id="24163-107">**Identificador de error:** BC31423</span><span class="sxs-lookup"><span data-stu-id="24163-107">**Error ID:** BC31423</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="24163-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="24163-108">To correct this error</span></span>

- <span data-ttu-id="24163-109">Implemente los eventos por separado.</span><span class="sxs-lookup"><span data-stu-id="24163-109">Implement the events separately.</span></span>

     <span data-ttu-id="24163-110">-O bien-</span><span class="sxs-lookup"><span data-stu-id="24163-110">—or—</span></span>

- <span data-ttu-id="24163-111">Defina los eventos en la interfaz mediante la `As` sintaxis y especifique el mismo tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="24163-111">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>

## <a name="see-also"></a><span data-ttu-id="24163-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="24163-112">See also</span></span>

- [<span data-ttu-id="24163-113">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="24163-113">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="24163-114">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="24163-114">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="24163-115">Eventos</span><span class="sxs-lookup"><span data-stu-id="24163-115">Events</span></span>](../../programming-guide/language-features/events/index.md)
