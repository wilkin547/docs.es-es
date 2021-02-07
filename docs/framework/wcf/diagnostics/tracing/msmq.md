---
description: 'Más información acerca de: MSMQ'
title: MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 3d694fdab202cd2b3b03c377f72d93c22cbae263
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720584"
---
# <a name="msmq"></a><span data-ttu-id="19da4-103">MSMQ</span><span class="sxs-lookup"><span data-stu-id="19da4-103">MSMQ</span></span>

<span data-ttu-id="19da4-104">En una aplicación MSMQ, no se transfiere ninguna actividad adicional del canal en cola a MSMQ y de MSMQ al canal en cola.</span><span class="sxs-lookup"><span data-stu-id="19da4-104">In an MSMQ application, no additional activity is transferred from the queued channel to MSMQ and from MSMQ to the queued channel.</span></span>  
  
 <span data-ttu-id="19da4-105">Además, se siguen tanto el id. de mensaje de MSMQ como el del mensaje SOAP (junto con el id. de la actividad, si existe) como seguimientos de canal en cola en una operación de envío.</span><span class="sxs-lookup"><span data-stu-id="19da4-105">In addition, MSMQ Message ID and SOAP message ID (along with Activity ID, if one exists) are traced as part of queued channel traces on a Send operation.</span></span>  
  
 <span data-ttu-id="19da4-106">Se siguen tanto el id. de mensaje de MSMQ como el del mensaje SOAP (junto con el id. de la actividad, si existe) como seguimientos de canal en cola en una operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="19da4-106">MSMQ Message ID and SOAP message ID (along with activity ID, if one exists) are traced as part of queued channel traces on a Receive operation.</span></span>  
  
 <span data-ttu-id="19da4-107">Las transferencias necesarias en la operación de recepción se ejecutan de forma similar a cualquier otro transporte (bytes de recepción->operación de > de mensajes de proceso).</span><span class="sxs-lookup"><span data-stu-id="19da4-107">The required transfers on the Receive operation are executed similarly to any other transport (receive bytes->Process message-> operation).</span></span>
