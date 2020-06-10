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
ms.openlocfilehash: 910ad952192243c6aa8a79417ad711d8c2a4ba2e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590545"
---
# <a name="reliable-sessions"></a><span data-ttu-id="1a409-102">Sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="1a409-102">Reliable Sessions</span></span>

<span data-ttu-id="1a409-103">En esta sección se describe qué es una sesión confiable de Windows Communication Foundation (WCF), para qué se usa, cómo y Cuándo usar una, qué configuraciones de enlace lo admiten y punteros en procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="1a409-103">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="1a409-104">La siguiente tabla resume los detalles sobre los puntos esenciales y temas relacionados de esta sección.</span><span class="sxs-lookup"><span data-stu-id="1a409-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="1a409-105">WCF de sesión confiable proporciona características que garantizan que los mensajes enviados entre los puntos de conexión se transfieren a través de intermediarios de transporte o SOAP y se entregan una sola vez y, opcionalmente, en el mismo orden en el que se enviaron.</span><span class="sxs-lookup"><span data-stu-id="1a409-105">The reliable session WCF provides features ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="1a409-106">Para utilizar una sesión confiable con una aplicación WCF, use uno de los enlaces proporcionados por el sistema en WCF que admitan una sesión confiable de forma predeterminada o como opción, o bien cree su propio enlace personalizado que admita la sesión.</span><span class="sxs-lookup"><span data-stu-id="1a409-106">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1a409-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1a409-107">In This Section</span></span>

<span data-ttu-id="1a409-108">[Información general de sesiones confiables](reliable-sessions-overview.md) Describe las sesiones confiables, Cuándo utilizarlas, los distintos enlaces que admiten sesiones confiables y cómo funcionan.</span><span class="sxs-lookup"><span data-stu-id="1a409-108">[Reliable Sessions Overview](reliable-sessions-overview.md) Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="1a409-109">[Cómo: intercambiar mensajes dentro de una sesión confiable](how-to-exchange-messages-within-a-reliable-session.md) Describe cómo crear una sesión confiable sobre HTTP mediante un enlace personalizado especificado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="1a409-109">[How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md) Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="1a409-110">[Cómo: proteger mensajes dentro de sesiones confiables](how-to-secure-messages-within-reliable-sessions.md) Describe cómo proteger una sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="1a409-110">[How to: Secure Messages within Reliable Sessions](how-to-secure-messages-within-reliable-sessions.md) Describes how to secure a reliable session.</span></span>

<span data-ttu-id="1a409-111">[Cómo: crear un enlace de sesión confiable personalizado con https](how-to-create-a-custom-reliable-session-binding-with-https.md) Describe cómo crear una sesión confiable sobre HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1a409-111">[How to: Create a Custom Reliable Session Binding with HTTPS](how-to-create-a-custom-reliable-session-binding-with-https.md) Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="1a409-112">[Prácticas recomendadas para sesiones confiables](best-practices-for-reliable-sessions.md) Describe algunas de las prácticas recomendadas asociadas con el uso de una sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="1a409-112">[Best Practices for Reliable Sessions](best-practices-for-reliable-sessions.md) Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="1a409-113">Referencia</span><span class="sxs-lookup"><span data-stu-id="1a409-113">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="1a409-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a409-114">See also</span></span>

- [<span data-ttu-id="1a409-115">Colas y sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="1a409-115">Queues and Reliable Sessions</span></span>](queues-and-reliable-sessions.md)
- [<span data-ttu-id="1a409-116">Sesiones, creación de instancias y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="1a409-116">Sessions, Instancing, and Concurrency</span></span>](sessions-instancing-and-concurrency.md)
