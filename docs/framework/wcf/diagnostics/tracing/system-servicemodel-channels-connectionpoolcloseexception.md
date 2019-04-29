---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: 3dd28276cd3a39497c0387f5b9d0adec23d07c37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666838"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="e5241-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="e5241-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="e5241-103">Se produjo una excepción al cerrar las conexiones de este grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="e5241-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e5241-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5241-104">Description</span></span>  
 <span data-ttu-id="e5241-105">Este seguimiento de nivel de error indica que se ha producido un error al cerrar los grupos de conexiones utilizados por la característica de agrupación de conexiones de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e5241-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="e5241-106">Una posible razón para que esto suceda es el cierre incorrecto de una conexión agrupada o un conjunto de conexiones agrupadas dentro del CloseTimeout.</span><span class="sxs-lookup"><span data-stu-id="e5241-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="e5241-107">Cuando se produce esta excepción, se anula cualquier conexión que permanezca abierta dentro de ese grupo y se abandonan las conexiones abiertas dentro de otros grupos.</span><span class="sxs-lookup"><span data-stu-id="e5241-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5241-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5241-108">See also</span></span>

- [<span data-ttu-id="e5241-109">Traza</span><span class="sxs-lookup"><span data-stu-id="e5241-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="e5241-110">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="e5241-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e5241-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e5241-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
