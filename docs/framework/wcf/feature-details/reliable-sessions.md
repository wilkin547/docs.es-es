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
ms.openlocfilehash: 9a2cd06c4c5a73d9fb5c4c7f09632e10c3eb0d87
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679139"
---
# <a name="reliable-sessions"></a><span data-ttu-id="a525c-102">Sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="a525c-102">Reliable Sessions</span></span>

<span data-ttu-id="a525c-103">En esta sección se describe qué un Windows Communication Foundation (WCF) sesión confiable es lo se usa, cómo y cuándo usar uno, qué configuraciones de enlace admiten e indicaciones sobre procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="a525c-103">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="a525c-104">La siguiente tabla resume los detalles sobre los puntos esenciales y temas relacionados de esta sección.</span><span class="sxs-lookup"><span data-stu-id="a525c-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="a525c-105">La sesión confiable WCF proporciona características que garantiza que los mensajes enviados entre puntos de conexión se transfieren a través de intermediarios de transporte o SOAP y se entregan una sola vez y, opcionalmente, en el mismo orden en que se enviaron.</span><span class="sxs-lookup"><span data-stu-id="a525c-105">The reliable session WCF provides features ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="a525c-106">Para utilizar una sesión confiable con una aplicación de WCF, use uno de los enlaces proporcionados por el sistema en WCF que admiten una sesión confiable de manera predeterminada o como una opción o crear su propio enlace personalizado que admita la sesión.</span><span class="sxs-lookup"><span data-stu-id="a525c-106">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a525c-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a525c-107">In This Section</span></span>

<span data-ttu-id="a525c-108">[Información general de las sesiones confiables](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) describe las sesiones confiables, cuándo utilizarlas, los distintos enlaces que admiten sesiones confiables, y cómo funcionan.</span><span class="sxs-lookup"><span data-stu-id="a525c-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="a525c-109">[Cómo: Exchange mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) se describe cómo crear una sesión confiable a través de HTTP mediante un enlace personalizado especificado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="a525c-109">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="a525c-110">[Cómo: Proteger los mensajes dentro de sesiones confiables](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) se describe cómo proteger una sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="a525c-110">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) Describes how to secure a reliable session.</span></span>

<span data-ttu-id="a525c-111">[Cómo: Creación de un enlace de la sesión confiable de personalizado con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) se describe cómo crear una sesión confiable a través de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a525c-111">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="a525c-112">[Procedimientos recomendados para las sesiones confiables](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) se describen algunos de los procedimientos recomendados relacionados con el uso de una sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="a525c-112">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="a525c-113">Referencia</span><span class="sxs-lookup"><span data-stu-id="a525c-113">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="a525c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a525c-114">See also</span></span>

- [<span data-ttu-id="a525c-115">Colas y sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="a525c-115">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [<span data-ttu-id="a525c-116">Sesiones, creación de instancias y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="a525c-116">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
