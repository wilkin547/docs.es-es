---
title: Otro registro de eventos ya ha registrado un origen con este nombre.
ms.date: 07/20/2015
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
ms.openlocfilehash: 333c28036e2d1b7514c7370b98ff70a6d195a9dd
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058396"
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="ddc63-102">Otro registro de eventos ya ha registrado un origen con este nombre.</span><span class="sxs-lookup"><span data-stu-id="ddc63-102">Another event log has already registered a source with this name</span></span>

<span data-ttu-id="ddc63-103">Se ha intentado escribir una entrada en un registro de eventos donde el origen especificado está registrado con otro registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="ddc63-103">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="ddc63-104">Debe establecer la propiedad <xref:System.Diagnostics.EventLog.Source%2A> de la instancia de componente <xref:System.Diagnostics.EventLog> antes de que el componente escriba una entrada en un registro.</span><span class="sxs-lookup"><span data-stu-id="ddc63-104">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="ddc63-105">Cuando ocurre esto, el sistema comprueba que el origen especificado está registrado con el registro de eventos en el que el componente está escribiendo y llama a <xref:System.Diagnostics.EventLog.CreateEventSource%2A> , si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ddc63-105">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ddc63-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ddc63-106">To correct this error</span></span>  
  
1. <span data-ttu-id="ddc63-107">Elimine la asociación del origen con el primer registro mediante el método <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> o <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> .</span><span class="sxs-lookup"><span data-stu-id="ddc63-107">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2. <span data-ttu-id="ddc63-108">Registre el origen con el nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="ddc63-108">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddc63-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddc63-109">See also</span></span>

- [<span data-ttu-id="ddc63-110">My. Application. log</span><span class="sxs-lookup"><span data-stu-id="ddc63-110">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
