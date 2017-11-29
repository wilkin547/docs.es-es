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
ms.openlocfilehash: 8beea344d233794ddc36d7fc53db1c01be84399f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="bf7ef-102">Otro registro de eventos ya ha registrado un origen con este nombre.</span><span class="sxs-lookup"><span data-stu-id="bf7ef-102">Another event log has already registered a source with this name</span></span>
<span data-ttu-id="bf7ef-103">Se ha intentado escribir una entrada en un registro de eventos donde el origen especificado está registrado con otro registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="bf7ef-103">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="bf7ef-104">Debe establecer la propiedad <xref:System.Diagnostics.EventLog.Source%2A> de la instancia de componente <xref:System.Diagnostics.EventLog> antes de que el componente escriba una entrada en un registro.</span><span class="sxs-lookup"><span data-stu-id="bf7ef-104">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="bf7ef-105">Cuando ocurre esto, el sistema comprueba que el origen especificado está registrado con el registro de eventos en el que el componente está escribiendo y llama a <xref:System.Diagnostics.EventLog.CreateEventSource%2A> , si es necesario.</span><span class="sxs-lookup"><span data-stu-id="bf7ef-105">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bf7ef-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="bf7ef-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="bf7ef-107">Elimine la asociación del origen con el primer registro mediante el método <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> o <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> .</span><span class="sxs-lookup"><span data-stu-id="bf7ef-107">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2.  <span data-ttu-id="bf7ef-108">Registre el origen con el nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="bf7ef-108">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf7ef-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf7ef-109">See Also</span></span>  
 [<span data-ttu-id="bf7ef-110">My.Application.Log (objeto)</span><span class="sxs-lookup"><span data-stu-id="bf7ef-110">My.Application.Log Object</span></span>](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [<span data-ttu-id="bf7ef-111">Cómo: quitar un origen de eventos</span><span class="sxs-lookup"><span data-stu-id="bf7ef-111">How to: Remove an Event Source</span></span>](http://msdn.microsoft.com/en-us/bc66c900-4b8a-426a-b8e2-17031a20167e)  
 [<span data-ttu-id="bf7ef-112">Cómo: agregar la aplicación como un origen de entradas de registro de eventos</span><span class="sxs-lookup"><span data-stu-id="bf7ef-112">How to: Add Your Application as a Source of Event Log Entries</span></span>](http://msdn.microsoft.com/en-us/948ff920-a739-4e66-a191-ee951512d42c)
