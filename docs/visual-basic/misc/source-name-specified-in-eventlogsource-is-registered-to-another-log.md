---
description: 'Más información acerca de: el nombre de origen especificado en EventLogSource se registra en un registro distinto del especificado en EventLogName'
title: El nombre de origen especificado en EventLogSource se registra en un registro distinto del especificado en EventLogName.
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: d6b9c1265276f94369d37e6ac55604b761fb9bcc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100455462"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a><span data-ttu-id="54c52-103">El nombre de origen especificado en EventLogSource se registra en un registro distinto del especificado en EventLogName.</span><span class="sxs-lookup"><span data-stu-id="54c52-103">Source name specified in EventLogSource is registered to a log other than that specified in EventLogName</span></span>

<span data-ttu-id="54c52-104">El `EventLog` intenta hacer referencia a un origen que está registrado en un registro diferente.</span><span class="sxs-lookup"><span data-stu-id="54c52-104">The `EventLog` is attempting to refer to a source that is registered to a different log.</span></span> <span data-ttu-id="54c52-105">Si va a escribir entradas en un registro de eventos, debe especificar la propiedad <xref:System.Diagnostics.EventLog.Source%2A> .</span><span class="sxs-lookup"><span data-stu-id="54c52-105">If you are writing entries to an event log, you must specify the <xref:System.Diagnostics.EventLog.Source%2A> property.</span></span> <span data-ttu-id="54c52-106">La propiedad <xref:System.Diagnostics.EventLog.Source%2A> registra el componente con el registro de eventos como un origen válido de entradas.</span><span class="sxs-lookup"><span data-stu-id="54c52-106">The <xref:System.Diagnostics.EventLog.Source%2A> property registers your component with the event log as a valid source of entries.</span></span> <span data-ttu-id="54c52-107">Un origen único se puede asociar (y, por tanto, escribir entradas) con un único registro de eventos a la vez.</span><span class="sxs-lookup"><span data-stu-id="54c52-107">A single source can be associated with (and therefore write entries to) only one event log at a time.</span></span>  
  
 <span data-ttu-id="54c52-108">De forma predeterminada, si intenta escribir una entrada sin haber registrado primero el componente como un origen válido, el sistema automáticamente registrará el origen con el registro de eventos, usando el valor de la propiedad <xref:System.Diagnostics.EventLog.Source%2A> como la cadena de origen.</span><span class="sxs-lookup"><span data-stu-id="54c52-108">By default, if you try to write an entry without first having registered your component as a valid source, the system automatically registers the source with the event log, using the value of the <xref:System.Diagnostics.EventLog.Source%2A> property as the source string.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="54c52-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="54c52-109">To correct this error</span></span>  
  
- <span data-ttu-id="54c52-110">Asegúrese de que el origen está registrado en el registro correcto.</span><span class="sxs-lookup"><span data-stu-id="54c52-110">Make sure the source is registered to the correct log.</span></span> <span data-ttu-id="54c52-111">Para ello, use el método <xref:System.Diagnostics.EventLog.CreateEventSource%2A> o una de sus sobrecargas para especificar una cadena que identifique de forma única el componente en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="54c52-111">To do this, use the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method or one of its overloads to specify a string that uniquely identifies your component to the event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54c52-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54c52-112">See also</span></span>

- <span data-ttu-id="54c52-113">[Administrar registros de eventos](/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="54c52-113">[Administering Event Logs](/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span></span>
- <span data-ttu-id="54c52-114">[Referencias del registro de eventos](/previous-versions/visualstudio/visual-studio-2008/k43k9z2a(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="54c52-114">[Event Log References](/previous-versions/visualstudio/visual-studio-2008/k43k9z2a(v=vs.90))</span></span>
- <span data-ttu-id="54c52-115">[Cómo: agregar una aplicación como origen de las entradas del registro de eventos](/previous-versions/visualstudio/visual-studio-2008/xz73e171(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="54c52-115">[How to: Add Your Application as a Source of Event Log Entries](/previous-versions/visualstudio/visual-studio-2008/xz73e171(v=vs.90))</span></span>
- <span data-ttu-id="54c52-116">[Cómo: quitar un origen de eventos](/previous-versions/visualstudio/visual-studio-2008/k57466fc(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="54c52-116">[How to: Remove an Event Source](/previous-versions/visualstudio/visual-studio-2008/k57466fc(v=vs.90))</span></span>
