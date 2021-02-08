---
description: 'Más información acerca de: otro registro de eventos ya ha registrado un origen con este nombre'
title: Otro registro de eventos ya ha registrado un origen con este nombre.
ms.date: 07/20/2015
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
ms.openlocfilehash: ec6ae0b3ef12452a0135e5bf17dbdd5844c0f478
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787362"
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="883e5-103">Otro registro de eventos ya ha registrado un origen con este nombre.</span><span class="sxs-lookup"><span data-stu-id="883e5-103">Another event log has already registered a source with this name</span></span>

<span data-ttu-id="883e5-104">Se ha intentado escribir una entrada en un registro de eventos donde el origen especificado está registrado con otro registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="883e5-104">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="883e5-105">Debe establecer la propiedad <xref:System.Diagnostics.EventLog.Source%2A> de la instancia de componente <xref:System.Diagnostics.EventLog> antes de que el componente escriba una entrada en un registro.</span><span class="sxs-lookup"><span data-stu-id="883e5-105">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="883e5-106">Cuando ocurre esto, el sistema comprueba que el origen especificado está registrado con el registro de eventos en el que el componente está escribiendo y llama a <xref:System.Diagnostics.EventLog.CreateEventSource%2A> , si es necesario.</span><span class="sxs-lookup"><span data-stu-id="883e5-106">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="883e5-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="883e5-107">To correct this error</span></span>  
  
1. <span data-ttu-id="883e5-108">Elimine la asociación del origen con el primer registro mediante el método <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> o <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> .</span><span class="sxs-lookup"><span data-stu-id="883e5-108">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2. <span data-ttu-id="883e5-109">Registre el origen con el nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="883e5-109">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="883e5-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="883e5-110">See also</span></span>

- [<span data-ttu-id="883e5-111">My. Application. log</span><span class="sxs-lookup"><span data-stu-id="883e5-111">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
