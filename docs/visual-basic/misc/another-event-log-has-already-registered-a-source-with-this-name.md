---
title: Otro registro de eventos ya ha registrado un origen con este nombre.
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f04afd5d061a44f572d95abfb0173ad6fa2ac27
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="d3051-102">Otro registro de eventos ya ha registrado un origen con este nombre.</span><span class="sxs-lookup"><span data-stu-id="d3051-102">Another event log has already registered a source with this name</span></span>
<span data-ttu-id="d3051-103">Se ha intentado escribir una entrada en un registro de eventos donde el origen especificado está registrado con otro registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="d3051-103">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="d3051-104">Debe establecer la propiedad <xref:System.Diagnostics.EventLog.Source%2A> de la instancia de componente <xref:System.Diagnostics.EventLog> antes de que el componente escriba una entrada en un registro.</span><span class="sxs-lookup"><span data-stu-id="d3051-104">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="d3051-105">Cuando ocurre esto, el sistema comprueba que el origen especificado está registrado con el registro de eventos en el que el componente está escribiendo y llama a <xref:System.Diagnostics.EventLog.CreateEventSource%2A> , si es necesario.</span><span class="sxs-lookup"><span data-stu-id="d3051-105">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d3051-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d3051-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="d3051-107">Elimine la asociación del origen con el primer registro mediante el método <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> o <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> .</span><span class="sxs-lookup"><span data-stu-id="d3051-107">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2.  <span data-ttu-id="d3051-108">Registre el origen con el nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="d3051-108">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3051-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3051-109">See Also</span></span>  
 [<span data-ttu-id="d3051-110">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="d3051-110">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)  

