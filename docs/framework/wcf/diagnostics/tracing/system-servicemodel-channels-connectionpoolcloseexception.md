---
description: 'Más información sobre: System. ServiceModel. Channels. ConnectionPoolCloseException'
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: a65739cc872f3cd175d76e9113380f9f4185d498
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99644637"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="1da07-103">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="1da07-103">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>

<span data-ttu-id="1da07-104">Se produjo una excepción al cerrar las conexiones de este grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="1da07-104">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1da07-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="1da07-105">Description</span></span>  

 <span data-ttu-id="1da07-106">Este seguimiento de nivel de error indica que se ha producido un error al cerrar los grupos de conexiones usados por la característica de agrupación de conexiones de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1da07-106">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="1da07-107">Una posible razón para que esto suceda es el cierre incorrecto de una conexión agrupada o un conjunto de conexiones agrupadas dentro del CloseTimeout.</span><span class="sxs-lookup"><span data-stu-id="1da07-107">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="1da07-108">Cuando se produce esta excepción, se anula cualquier conexión que permanezca abierta dentro de ese grupo y se abandonan las conexiones abiertas dentro de otros grupos.</span><span class="sxs-lookup"><span data-stu-id="1da07-108">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1da07-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="1da07-109">See also</span></span>

- [<span data-ttu-id="1da07-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="1da07-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="1da07-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="1da07-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1da07-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1da07-112">Administration and Diagnostics</span></span>](../index.md)
