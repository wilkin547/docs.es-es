---
title: El evento '<eventname1>' no puede implementar el evento '<eventname2>' en la interfaz '<interface>' porque sus tipos delegados '<delegate1>' y '<delegate2>' no coinciden
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 3ec3e7bb2f28bf8c4dd38bc71e11193456860021
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379762"
---
# <a name="event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a><span data-ttu-id="f220c-102">Evento '\<eventname1 >' no se puede implementar el evento '\<eventname2 >' en la interfaz '\<interfaz >' porque sus tipos de delegado\<delegate1 >' y '\<delegate2 >' no coinciden</span><span class="sxs-lookup"><span data-stu-id="f220c-102">Event '\<eventname1>' cannot implement event '\<eventname2>' on interface '\<interface>' because their delegate types '\<delegate1>' and '\<delegate2>' do not match</span></span>
<span data-ttu-id="f220c-103">Visual Basic no puede implementar un evento porque el tipo de delegado del evento no coincide con el tipo de delegado del evento en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="f220c-103">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="f220c-104">Este error puede producirse cuando define varios eventos en una interfaz e intenta implementarlos juntos con el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="f220c-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="f220c-105">Un evento puede implementar dos o más eventos solo si todos los eventos implementados se declaran con la sintaxis `As` y si se especifica el mismo tipo delegado.</span><span class="sxs-lookup"><span data-stu-id="f220c-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="f220c-106">**Identificador de error:** BC31423</span><span class="sxs-lookup"><span data-stu-id="f220c-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f220c-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f220c-107">To correct this error</span></span>  
  
-   <span data-ttu-id="f220c-108">Implemente los eventos por separado.</span><span class="sxs-lookup"><span data-stu-id="f220c-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="f220c-109">-O bien-</span><span class="sxs-lookup"><span data-stu-id="f220c-109">—or—</span></span>  
  
-   <span data-ttu-id="f220c-110">Definir los eventos en la interfaz usando el `As` sintaxis y especifique el mismo tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="f220c-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f220c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f220c-111">See also</span></span>
- [<span data-ttu-id="f220c-112">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f220c-112">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="f220c-113">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f220c-113">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="f220c-114">Eventos</span><span class="sxs-lookup"><span data-stu-id="f220c-114">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
