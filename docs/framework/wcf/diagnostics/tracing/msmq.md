---
title: MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 7ef31a188e1564da47ea1e7323cdd4cd5ef5be60
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236681"
---
# <a name="msmq"></a><span data-ttu-id="b5dc8-102">MSMQ</span><span class="sxs-lookup"><span data-stu-id="b5dc8-102">MSMQ</span></span>

<span data-ttu-id="b5dc8-103">En una aplicación MSMQ, no se transfiere ninguna actividad adicional del canal en cola a MSMQ y de MSMQ al canal en cola.</span><span class="sxs-lookup"><span data-stu-id="b5dc8-103">In an MSMQ application, no additional activity is transferred from the queued channel to MSMQ and from MSMQ to the queued channel.</span></span>  
  
 <span data-ttu-id="b5dc8-104">Además, se siguen tanto el id. de mensaje de MSMQ como el del mensaje SOAP (junto con el id. de la actividad, si existe) como seguimientos de canal en cola en una operación de envío.</span><span class="sxs-lookup"><span data-stu-id="b5dc8-104">In addition, MSMQ Message ID and SOAP message ID (along with Activity ID, if one exists) are traced as part of queued channel traces on a Send operation.</span></span>  
  
 <span data-ttu-id="b5dc8-105">Se siguen tanto el id. de mensaje de MSMQ como el del mensaje SOAP (junto con el id. de la actividad, si existe) como seguimientos de canal en cola en una operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="b5dc8-105">MSMQ Message ID and SOAP message ID (along with activity ID, if one exists) are traced as part of queued channel traces on a Receive operation.</span></span>  
  
 <span data-ttu-id="b5dc8-106">Las transferencias necesarias en la operación de recepción se ejecutan de forma similar a cualquier otro transporte (bytes de recepción->operación de > de mensajes de proceso).</span><span class="sxs-lookup"><span data-stu-id="b5dc8-106">The required transfers on the Receive operation are executed similarly to any other transport (receive bytes->Process message-> operation).</span></span>
