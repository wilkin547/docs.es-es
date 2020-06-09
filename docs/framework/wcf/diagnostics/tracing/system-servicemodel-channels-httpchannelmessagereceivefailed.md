---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: e11b376924ee74e5d0d67da0cac59af41655dc44
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594080"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="47712-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="47712-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>
<span data-ttu-id="47712-103">Error al recibir un mensaje a través de un canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="47712-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="47712-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="47712-104">Description</span></span>  
 <span data-ttu-id="47712-105">Este seguimiento de traza puede emitirse como una advertencia o un error.</span><span class="sxs-lookup"><span data-stu-id="47712-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="47712-106">En ambos casos, el seguimiento se emite si no se encuentra un agente de escucha compatible para una solicitud HTTP entrante, y se descarta la solicitud.</span><span class="sxs-lookup"><span data-stu-id="47712-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="47712-107">Esto podría suceder si el agente de escucha no reconociese el verbo HTTP de la solicitud, o si el agente realizase la escucha en la dirección a la que está destinada la solicitud.</span><span class="sxs-lookup"><span data-stu-id="47712-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="47712-108">El seguimiento de traza se emite como advertencia en caso de autohospedaje, y como error si el servicio se hospeda en IIS.</span><span class="sxs-lookup"><span data-stu-id="47712-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47712-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="47712-109">See also</span></span>

- [<span data-ttu-id="47712-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="47712-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="47712-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="47712-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="47712-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="47712-112">Administration and Diagnostics</span></span>](../index.md)
