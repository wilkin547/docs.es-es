---
title: Sesiones de confianza
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 16480996b96145873b1d1f84d56af6d1aa863710
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-sessions"></a><span data-ttu-id="ed46f-102">Sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="ed46f-102">Reliable Sessions</span></span>

<span data-ttu-id="ed46f-103">Esta sección describe un [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sesión confiable es, lo que se usa, cómo y cuándo usar uno, qué configuraciones de enlace admiten e indicaciones sobre procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="ed46f-103">This section describes what a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="ed46f-104">La siguiente tabla resume los detalles sobre los puntos esenciales y temas relacionados de esta sección.</span><span class="sxs-lookup"><span data-stu-id="ed46f-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="ed46f-105">La sesión confiable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona funciones de asegurarse de que los mensajes enviados entre extremos se transfieren a través de intermediarios de transporte o SOAP y se entregan una sola vez y, opcionalmente, en el mismo orden en que se enviaron.</span><span class="sxs-lookup"><span data-stu-id="ed46f-105">The reliable session [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides featrues ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="ed46f-106">Para utilizar una sesión confiable con una aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], utilice uno de los enlaces proporcionados por el sistema en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que admiten una sesión confiable de forma predeterminada u opcional, o cree su propio enlace personalizado que admita la sesión.</span><span class="sxs-lookup"><span data-stu-id="ed46f-106">To use a reliable session with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, either use one of the system-provided bindings in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ed46f-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ed46f-107">In This Section</span></span>

<span data-ttu-id="ed46f-108">[Información general de las sesiones confiables](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="ed46f-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span></span>  
<span data-ttu-id="ed46f-109">Describe las sesiones confiables, cuándo utilizarlas, los diferentes enlaces que admiten las sesiones confiables y cómo funcionan.</span><span class="sxs-lookup"><span data-stu-id="ed46f-109">Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="ed46f-110">[Cómo: intercambiar mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span><span class="sxs-lookup"><span data-stu-id="ed46f-110">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span></span>  
<span data-ttu-id="ed46f-111">Describe cómo crear una sesión confiable sobre HTTP utilizando un enlace personalizado especificado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="ed46f-111">Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="ed46f-112">[Cómo: proteger los mensajes dentro de las sesiones confiables](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="ed46f-112">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span></span>  
<span data-ttu-id="ed46f-113">Describe cómo proteger una sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="ed46f-113">Describes how to secure a reliable session.</span></span>

<span data-ttu-id="ed46f-114">[Cómo: crear un enlace personalizado de sesión confiable con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span><span class="sxs-lookup"><span data-stu-id="ed46f-114">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span></span>  
<span data-ttu-id="ed46f-115">Describe cómo crear una sesión confiable sobre HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ed46f-115">Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="ed46f-116">[Prácticas recomendadas para las sesiones confiables](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="ed46f-116">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span></span>  
<span data-ttu-id="ed46f-117">Describe algunos de los procedimientos recomendados asociados al uso de una sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="ed46f-117">Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="ed46f-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="ed46f-118">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="ed46f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed46f-119">See Also</span></span>

<span data-ttu-id="ed46f-120">[Las colas y sesiones confiables](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="ed46f-120">[Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md) </span></span>  
[<span data-ttu-id="ed46f-121">Sesiones, creación de instancias y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="ed46f-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
