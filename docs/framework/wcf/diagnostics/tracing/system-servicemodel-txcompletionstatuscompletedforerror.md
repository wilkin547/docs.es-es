---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25106bffe6d541a89c786035db3d3266d861fd5b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="c98d8-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="c98d8-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="c98d8-103">La transacción especificada para la operación especificada se completó debido a una excepción de ejecución no controlada.</span><span class="sxs-lookup"><span data-stu-id="c98d8-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c98d8-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="c98d8-104">Description</span></span>  
 <span data-ttu-id="c98d8-105">Se efectúa el seguimiento cuando se produce un error durante un intento de completar la transacción actual.</span><span class="sxs-lookup"><span data-stu-id="c98d8-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="c98d8-106">Esto sucede antes de que se envíe una respuesta o un error al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c98d8-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="c98d8-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="c98d8-107">Troubleshooting</span></span>  
 <span data-ttu-id="c98d8-108">Busque en el mensaje de seguimiento el mensaje de excepción y cualquier elemento procesable.</span><span class="sxs-lookup"><span data-stu-id="c98d8-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c98d8-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c98d8-109">See Also</span></span>  
 [<span data-ttu-id="c98d8-110">Traza</span><span class="sxs-lookup"><span data-stu-id="c98d8-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="c98d8-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="c98d8-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="c98d8-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c98d8-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
