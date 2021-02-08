---
description: 'Más información sobre: System. ServiceModel. Channels. MsmqMoveOrDeleteAttemptFailed'
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: 7b3c8dad9e3a3e88dff72706917f3729d55b3799
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769746"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="a1e37-103">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="a1e37-103">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>

<span data-ttu-id="a1e37-104">No puede mover o eliminar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1e37-104">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a1e37-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1e37-105">Description</span></span>  

 <span data-ttu-id="a1e37-106">El seguimiento indica que se produjo un error al intentar mover, eliminar o rechazar un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="a1e37-106">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="a1e37-107">Windows Communication Foundation (WCF) emplean los mensajes de MSMQ (cuando se usan con NetMsmqBinding o MsmqIntegrationBinding). Este seguimiento está relacionado con el valor elegido de la `ReceiveErrorHandling` propiedad en NetMsmqBinding o MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="a1e37-107">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="a1e37-108">Este seguimiento no indica un error general del sistema.</span><span class="sxs-lookup"><span data-stu-id="a1e37-108">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="a1e37-109">Sin embargo, indica que la disposición del mensaje dudoso escogida produjo un error en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1e37-109">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="a1e37-110">Para obtener más información sobre cuándo los mensajes son dudosos y cómo configurar el servicio para controlarlos adecuadamente, vea [control de mensajes dudosos](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="a1e37-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1e37-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1e37-111">See also</span></span>

- [<span data-ttu-id="a1e37-112">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="a1e37-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="a1e37-113">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="a1e37-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="a1e37-114">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="a1e37-114">Administration and Diagnostics</span></span>](../index.md)
