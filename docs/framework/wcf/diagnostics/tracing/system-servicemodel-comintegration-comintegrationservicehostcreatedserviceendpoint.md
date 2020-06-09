---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: 8b81cdcaf74aca044260495867b2c4f1de517682
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593755"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="17e44-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="17e44-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="17e44-103">No puede mover o eliminar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="17e44-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="17e44-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="17e44-104">Description</span></span>  
 <span data-ttu-id="17e44-105">El seguimiento indica que se produjo un error al intentar mover, eliminar o rechazar un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="17e44-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="17e44-106">Windows Communication Foundation (WCF) emplean los mensajes de MSMQ (cuando se usan con NetMsmqBinding o MsmqIntegrationBinding). Este seguimiento está relacionado con el valor elegido de la `ReceiveErrorHandling` propiedad en NetMsmqBinding o MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="17e44-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="17e44-107">Este seguimiento no indica un error general del sistema.</span><span class="sxs-lookup"><span data-stu-id="17e44-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="17e44-108">Sin embargo, indica que la disposición del mensaje dudoso escogida produjo un error en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="17e44-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="17e44-109">Para obtener más información sobre cuándo los mensajes son dudosos y cómo configurar el servicio para controlarlos adecuadamente, vea [control de mensajes dudosos](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="17e44-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17e44-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="17e44-110">See also</span></span>

- [<span data-ttu-id="17e44-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="17e44-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="17e44-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="17e44-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="17e44-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="17e44-113">Administration and Diagnostics</span></span>](../index.md)
