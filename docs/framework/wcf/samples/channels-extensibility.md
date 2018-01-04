---
title: Extensibilidad de los canales
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 541770db6b9cc624fd08ab4db275bc63fa5deca9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="channels-extensibility"></a><span data-ttu-id="cf4a0-102">Extensibilidad de los canales</span><span class="sxs-lookup"><span data-stu-id="cf4a0-102">Channels Extensibility</span></span>
<span data-ttu-id="cf4a0-103">Esta sección contiene ejemplos que muestran los canales personalizados.</span><span class="sxs-lookup"><span data-stu-id="cf4a0-103">This section contains samples that demonstrate custom channels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf4a0-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cf4a0-104">In This Section</span></span>  
 [<span data-ttu-id="cf4a0-105">Canal local</span><span class="sxs-lookup"><span data-stu-id="cf4a0-105">Local Channel</span></span>](../../../../docs/framework/wcf/samples/local-channel.md)  
 <span data-ttu-id="cf4a0-106">Muestra el canal local, un canal de transporte de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se utiliza para la comunicación dentro del mismo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="cf4a0-106">Demonstrates the local channel, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transport channel that is used for communication within the same application domain.</span></span>  
  
 [<span data-ttu-id="cf4a0-107">Perfil seguro confiable</span><span class="sxs-lookup"><span data-stu-id="cf4a0-107">Reliable Secure Profile</span></span>](../../../../docs/framework/wcf/samples/reliable-secure-profile.md)  
 <span data-ttu-id="cf4a0-108">Muestra cómo crear [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y un perfil de protección confiable (RSP, Reliable Secure Profile).</span><span class="sxs-lookup"><span data-stu-id="cf4a0-108">Demonstrates how to compose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and Reliable Secure Profile (RSP).</span></span>  
  
 [<span data-ttu-id="cf4a0-109">Distribuidor de canal personalizado</span><span class="sxs-lookup"><span data-stu-id="cf4a0-109">Custom Channel Dispatcher</span></span>](../../../../docs/framework/wcf/samples/custom-channel-dispatcher.md)  
 <span data-ttu-id="cf4a0-110">Muestra cómo crear la pila del canal de manera personalizada implementando <xref:System.ServiceModel.ServiceHostBase> directamente y cómo crear un distribuidor de canal personalizado en un entorno de host web.</span><span class="sxs-lookup"><span data-stu-id="cf4a0-110">Demonstrates how to build the channel stack in a custom way by implementing <xref:System.ServiceModel.ServiceHostBase> directly and how to create a custom channel dispatcher in Web host environment.</span></span>  
  
 [<span data-ttu-id="cf4a0-111">Canal de fragmentación</span><span class="sxs-lookup"><span data-stu-id="cf4a0-111">Chunking Channel</span></span>](../../../../docs/framework/wcf/samples/chunking-channel.md)  
 <span data-ttu-id="cf4a0-112">Muestra cómo limitar la cantidad de memoria que se usa para almacenar en búfer los mensajes grandes enviados con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf4a0-112">Demonstrates how to limit the amount of memory used to buffer large messages sent using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="cf4a0-113">Canal de confirmación de HTTP</span><span class="sxs-lookup"><span data-stu-id="cf4a0-113">HTTP Acknowledgement Channel</span></span>](../../../../docs/framework/wcf/samples/http-acknowledgement-channel.md)  
 <span data-ttu-id="cf4a0-114">Muestra un canal en niveles que cambia el patrón de mensajería unidireccional.</span><span class="sxs-lookup"><span data-stu-id="cf4a0-114">Demonstrates a layered channel which changes the one-way messaging pattern.</span></span>  
  
 [<span data-ttu-id="cf4a0-115">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="cf4a0-115">HttpCookieSession</span></span>](../../../../docs/framework/wcf/samples/httpcookiesession.md)  
 <span data-ttu-id="cf4a0-116">Muestra cómo crear un canal de protocolo personalizado para usar cookies de HTTP para la administración de sesiones.</span><span class="sxs-lookup"><span data-stu-id="cf4a0-116">Demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span>  
  
 [<span data-ttu-id="cf4a0-117">Interceptador de mensajes personalizados</span><span class="sxs-lookup"><span data-stu-id="cf4a0-117">Custom Message Interceptor</span></span>](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)  
 <span data-ttu-id="cf4a0-118">Muestra cómo implementar un elemento de enlace personalizado que crea generadores de canales y agentes de escucha de canales para interceptar todos los mensajes entrantes y salientes en un punto concreto en la pila de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cf4a0-118">Demonstrates how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span>
