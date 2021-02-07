---
description: Más información acerca de cómo extender la capa de canal
title: Extensión de la capa de canales
ms.date: 03/30/2017
helpviewer_keywords:
- extending channels [WCF]
ms.assetid: 4238db74-2fb6-4dc8-a326-f58527230810
ms.openlocfilehash: 4588a2749127e454801615cc8916d83fc15592bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685587"
---
# <a name="extending-the-channel-layer"></a><span data-ttu-id="a1b45-103">Extensión de la capa de canales</span><span class="sxs-lookup"><span data-stu-id="a1b45-103">Extending the Channel Layer</span></span>

<span data-ttu-id="a1b45-104">La capa de canales es responsable del intercambio de mensajes entre clientes y servicios.</span><span class="sxs-lookup"><span data-stu-id="a1b45-104">The channel layer is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="a1b45-105">Las extensiones de canal pueden implementar nueva funcionalidad de protocolo, como seguridad o funcionalidad de transporte, como implementar un nuevo transporte de red para llevar los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="a1b45-105">Channel extensions can implement new protocol functionality, such as security, or transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1b45-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a1b45-106">In This Section</span></span>  

 [<span data-ttu-id="a1b45-107">Información general del modelo de canales</span><span class="sxs-lookup"><span data-stu-id="a1b45-107">Channel Model Overview</span></span>](channel-model-overview.md)  
 <span data-ttu-id="a1b45-108">Proporciona una información general de alto nivel de qué canales son, las características que proporcionan y cómo funcionan tanto en una aplicación de servicio como de cliente.</span><span class="sxs-lookup"><span data-stu-id="a1b45-108">Provides a high-level overview of what channels are, the features that they provide and how they work both in a service and a client application.</span></span>  
  
 [<span data-ttu-id="a1b45-109">Desarrollo de canales</span><span class="sxs-lookup"><span data-stu-id="a1b45-109">Developing Channels</span></span>](developing-channels.md)  
 <span data-ttu-id="a1b45-110">Describe a fondo las funciones que representan los diversos tipos de infraestructuras de canales, cómo funciona el motor de estado y el ciclo de vida de estado, cómo administrar excepciones y errores, cómo implementar la compatibilidad de metadatos y cómo funcionan los canales con codificadores de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a1b45-110">Describes in depth the roles that the various channel infrastructure types play, how the state engine and state lifecycle works, how to handle exceptions and faults, how to implement metadata support, and how channels work with message encoders.</span></span>  
  
 [<span data-ttu-id="a1b45-111">Codificadores personalizados</span><span class="sxs-lookup"><span data-stu-id="a1b45-111">Custom Encoders</span></span>](custom-encoders.md)  
 <span data-ttu-id="a1b45-112">Describe el papel que los codificadores del mensaje juegan en los canales y cómo crear uno.</span><span class="sxs-lookup"><span data-stu-id="a1b45-112">Describes the role that message encoders play in channels and how to build one.</span></span>  
  
 [<span data-ttu-id="a1b45-113">Actualizaciones personalizadas de secuencias</span><span class="sxs-lookup"><span data-stu-id="a1b45-113">Custom Stream Upgrades</span></span>](custom-stream-upgrades.md)  
 <span data-ttu-id="a1b45-114">Describe el proceso de actualización de las secuencias proporcionadas mediante transportes orientados a secuencias.</span><span class="sxs-lookup"><span data-stu-id="a1b45-114">Describes the process of upgrading the streams provided by stream-oriented transports.</span></span>
