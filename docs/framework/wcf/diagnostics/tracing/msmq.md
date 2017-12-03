---
title: MSMQ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15be4b6bfb84a0aa843e3d62861a9195e125a04e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="msmq"></a><span data-ttu-id="96173-102">MSMQ</span><span class="sxs-lookup"><span data-stu-id="96173-102">MSMQ</span></span>
<span data-ttu-id="96173-103">En una aplicación MSMQ, no se transfiere ninguna actividad adicional del canal en cola a MSMQ y de MSMQ al canal en cola.</span><span class="sxs-lookup"><span data-stu-id="96173-103">In an MSMQ application, no additional activity is transferred from the queued channel to MSMQ and from MSMQ to the queued channel.</span></span>  
  
 <span data-ttu-id="96173-104">Además, se siguen tanto el id. de mensaje de MSMQ como el del mensaje SOAP (junto con el id. de la actividad, si existe) como seguimientos de canal en cola en una operación de envío.</span><span class="sxs-lookup"><span data-stu-id="96173-104">In addition, MSMQ Message ID and SOAP message ID (along with Activity ID, if one exists) are traced as part of queued channel traces on a Send operation.</span></span>  
  
 <span data-ttu-id="96173-105">Se siguen tanto el id. de mensaje de MSMQ como el del mensaje SOAP (junto con el id. de la actividad, si existe) como seguimientos de canal en cola en una operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="96173-105">MSMQ Message ID and SOAP message ID (along with activity ID, if one exists) are traced as part of queued channel traces on a Receive operation.</span></span>  
  
 <span data-ttu-id="96173-106">Las transferencias necesarias en la operación de recepción se ejecutan de igual forma que en cualquier otro transporte (operación de recepción de bytes ->Procese mensaje ->).</span><span class="sxs-lookup"><span data-stu-id="96173-106">The required transfers on the Receive operation are executed similarly to any other transport (receive bytes->Process message-> operation).</span></span>
