---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.date: 03/30/2017
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
ms.openlocfilehash: 59bba87095931c80a7ce347def2656a7a1f6f949
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33479323"
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a><span data-ttu-id="bc6ef-102">System.ServiceModel.Channels.FailedAcceptFromPool</span><span class="sxs-lookup"><span data-stu-id="bc6ef-102">System.ServiceModel.Channels.FailedAcceptFromPool</span></span>
<span data-ttu-id="bc6ef-103">Error en un intento para usar de nuevo una conexión agrupada.</span><span class="sxs-lookup"><span data-stu-id="bc6ef-103">An attempt to reuse a pooled connection failed.</span></span> <span data-ttu-id="bc6ef-104">Se realiza otro intento dentro del período de tiempo de espera especificado.</span><span class="sxs-lookup"><span data-stu-id="bc6ef-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bc6ef-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc6ef-105">Description</span></span>  
 <span data-ttu-id="bc6ef-106">Este seguimiento de información indica que se ha producido un error mientras se intentaba reutilizar una conexión de grupo.</span><span class="sxs-lookup"><span data-stu-id="bc6ef-106">This informational trace indicates that an error has occurred while attempting to reuse a pooled connection.</span></span> <span data-ttu-id="bc6ef-107">Esto podría haber pasado porque la conexión de grupo no era compatible, no estaba preparada o estaba aún activa.</span><span class="sxs-lookup"><span data-stu-id="bc6ef-107">This could happen because the pooled connection was not compatible, ready, or still active.</span></span> <span data-ttu-id="bc6ef-108">Hay un tiempo establecido para realizar intentos adicionales de reutilizar otra conexión de grupo, y en caso de que no se encuentren conexiones utilizables, se crea una nueva.</span><span class="sxs-lookup"><span data-stu-id="bc6ef-108">Additional attempts to reuse other pooled connection are made within a given timeout and a new connection is created in case no usable connections are found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc6ef-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc6ef-109">See Also</span></span>  
 [<span data-ttu-id="bc6ef-110">Traza</span><span class="sxs-lookup"><span data-stu-id="bc6ef-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="bc6ef-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="bc6ef-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="bc6ef-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="bc6ef-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
