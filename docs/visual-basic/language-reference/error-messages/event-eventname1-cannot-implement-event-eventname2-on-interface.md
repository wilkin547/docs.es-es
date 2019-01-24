---
title: Evento &#39; &lt;eventname1&gt; &#39; no se puede implementar el evento &#39; &lt;eventname2&gt; &#39; en interfaz &#39; &lt;interfaz&gt; &#39; porque sus tipos delegados &#39; &lt;delegate1&gt; &#39; y &#39; &lt;delegate2&gt; &#39; no coinciden
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 024e260f12d3497d64f26e59521f016ad439ebb6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638219"
---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a><span data-ttu-id="4b915-102">Evento &#39; &lt;eventname1&gt; &#39; no se puede implementar el evento &#39; &lt;eventname2&gt; &#39; en interfaz &#39; &lt;interfaz&gt; &#39; porque sus tipos delegados &#39; &lt;delegate1&gt; &#39; y &#39; &lt;delegate2&gt; &#39; no coinciden</span><span class="sxs-lookup"><span data-stu-id="4b915-102">Event &#39;&lt;eventname1&gt;&#39; cannot implement event &#39;&lt;eventname2&gt;&#39; on interface &#39;&lt;interface&gt;&#39; because their delegate types &#39;&lt;delegate1&gt;&#39; and &#39;&lt;delegate2&gt;&#39; do not match</span></span>
<span data-ttu-id="4b915-103">Visual Basic no puede implementar un evento porque el tipo de delegado del evento no coincide con el tipo de delegado del evento en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="4b915-103">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="4b915-104">Este error puede producirse cuando define varios eventos en una interfaz e intenta implementarlos juntos con el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="4b915-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="4b915-105">Un evento puede implementar dos o más eventos solo si todos los eventos implementados se declaran con la sintaxis `As` y si se especifica el mismo tipo delegado.</span><span class="sxs-lookup"><span data-stu-id="4b915-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="4b915-106">**Identificador de error:** BC31423</span><span class="sxs-lookup"><span data-stu-id="4b915-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4b915-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4b915-107">To correct this error</span></span>  
  
-   <span data-ttu-id="4b915-108">Implemente los eventos por separado.</span><span class="sxs-lookup"><span data-stu-id="4b915-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="4b915-109">-O bien-</span><span class="sxs-lookup"><span data-stu-id="4b915-109">—or—</span></span>  
  
-   <span data-ttu-id="4b915-110">Definir los eventos en la interfaz usando el `As` sintaxis y especifique el mismo tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="4b915-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b915-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b915-111">See also</span></span>
- [<span data-ttu-id="4b915-112">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4b915-112">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="4b915-113">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4b915-113">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="4b915-114">Eventos</span><span class="sxs-lookup"><span data-stu-id="4b915-114">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
