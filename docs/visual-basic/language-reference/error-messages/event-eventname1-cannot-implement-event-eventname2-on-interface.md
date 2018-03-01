---
title: Evento &#39; &lt;eventname1&gt;&#39; no puede implementar el evento &#39;&lt; eventname2&gt;&#39; de interfaz &#39;&lt; interfaz&gt;&#39; porque sus tipos de delegado &#39;&lt; Delegate1&gt;&#39; y &#39;&lt; delegate2&gt;&#39; no coinciden
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b0fcbbf8a6e23270e4dcbf9d813c773e1522a92a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a><span data-ttu-id="e30a2-102">Evento &#39; &lt;eventname1&gt;&#39; no puede implementar el evento &#39;&lt; eventname2&gt;&#39; de interfaz &#39;&lt; interfaz&gt;&#39; porque sus tipos de delegado &#39;&lt; Delegate1&gt;&#39; y &#39;&lt; delegate2&gt;&#39; no coinciden</span><span class="sxs-lookup"><span data-stu-id="e30a2-102">Event &#39;&lt;eventname1&gt;&#39; cannot implement event &#39;&lt;eventname2&gt;&#39; on interface &#39;&lt;interface&gt;&#39; because their delegate types &#39;&lt;delegate1&gt;&#39; and &#39;&lt;delegate2&gt;&#39; do not match</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="e30a2-103">no se puede implementar un evento porque el tipo de delegado del evento no coincide con el tipo de delegado del evento de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="e30a2-103"> cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="e30a2-104">Este error puede producirse cuando define varios eventos en una interfaz e intenta implementarlos juntos con el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="e30a2-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="e30a2-105">Un evento puede implementar dos o más eventos solo si todos los eventos implementados se declaran con la sintaxis `As` y si se especifica el mismo tipo delegado.</span><span class="sxs-lookup"><span data-stu-id="e30a2-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="e30a2-106">**Id. de error:** BC31423</span><span class="sxs-lookup"><span data-stu-id="e30a2-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e30a2-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e30a2-107">To correct this error</span></span>  
  
-   <span data-ttu-id="e30a2-108">Implemente los eventos por separado.</span><span class="sxs-lookup"><span data-stu-id="e30a2-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="e30a2-109">-O bien-</span><span class="sxs-lookup"><span data-stu-id="e30a2-109">—or—</span></span>  
  
-   <span data-ttu-id="e30a2-110">Definir los eventos en la interfaz con el `As` sintaxis y especifican el mismo tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="e30a2-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e30a2-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e30a2-111">See Also</span></span>  
 [<span data-ttu-id="e30a2-112">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e30a2-112">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="e30a2-113">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e30a2-113">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="e30a2-114">Eventos</span><span class="sxs-lookup"><span data-stu-id="e30a2-114">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
