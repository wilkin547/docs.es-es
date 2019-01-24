---
title: Sesiones de confianza
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 1d87f6f4d94763dc8f6ac7e929c22b17940097ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735430"
---
# <a name="reliable-sessions"></a><span data-ttu-id="1fc50-102">Sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="1fc50-102">Reliable Sessions</span></span>

<span data-ttu-id="1fc50-103">En esta sección se describe qué un Windows Communication Foundation (WCF) sesión confiable es lo se usa, cómo y cuándo usar uno, qué configuraciones de enlace admiten e indicaciones sobre procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="1fc50-103">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="1fc50-104">La siguiente tabla resume los detalles sobre los puntos esenciales y temas relacionados de esta sección.</span><span class="sxs-lookup"><span data-stu-id="1fc50-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="1fc50-105">La sesión confiable WCF proporciona funciones que garantiza que los mensajes enviados entre puntos de conexión se transfieren a través de intermediarios de transporte o SOAP y se entregan una sola vez y, opcionalmente, en el mismo orden en que se enviaron.</span><span class="sxs-lookup"><span data-stu-id="1fc50-105">The reliable session WCF provides featrues ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="1fc50-106">Para utilizar una sesión confiable con una aplicación de WCF, use uno de los enlaces proporcionados por el sistema en WCF que admiten una sesión confiable de manera predeterminada o como una opción o crear su propio enlace personalizado que admita la sesión.</span><span class="sxs-lookup"><span data-stu-id="1fc50-106">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1fc50-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1fc50-107">In This Section</span></span>

<span data-ttu-id="1fc50-108">[Información general de las sesiones confiables](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="1fc50-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span></span>  
<span data-ttu-id="1fc50-109">Describe las sesiones confiables, cuándo utilizarlas, los diferentes enlaces que admiten las sesiones confiables y cómo funcionan.</span><span class="sxs-lookup"><span data-stu-id="1fc50-109">Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="1fc50-110">[Cómo: Mensajes de Exchange dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span><span class="sxs-lookup"><span data-stu-id="1fc50-110">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span></span>  
<span data-ttu-id="1fc50-111">Describe cómo crear una sesión confiable sobre HTTP utilizando un enlace personalizado especificado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="1fc50-111">Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="1fc50-112">[Cómo: Proteger los mensajes dentro de sesiones confiables](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="1fc50-112">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span></span>  
<span data-ttu-id="1fc50-113">Describe cómo proteger una sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="1fc50-113">Describes how to secure a reliable session.</span></span>

<span data-ttu-id="1fc50-114">[Cómo: Creación de un enlace personalizado de sesión confiable con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span><span class="sxs-lookup"><span data-stu-id="1fc50-114">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span></span>  
<span data-ttu-id="1fc50-115">Describe cómo crear una sesión confiable sobre HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1fc50-115">Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="1fc50-116">[Procedimientos recomendados para las sesiones confiables](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="1fc50-116">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span></span>  
<span data-ttu-id="1fc50-117">Describe algunos de los procedimientos recomendados asociados al uso de una sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="1fc50-117">Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="1fc50-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="1fc50-118">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="1fc50-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fc50-119">See also</span></span>

- [<span data-ttu-id="1fc50-120">Colas y sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="1fc50-120">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [<span data-ttu-id="1fc50-121">Sesiones, creación de instancias y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="1fc50-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
