---
title: "Extensión de ServiceHost y la capa de modelos de servicios"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extending service models [WCF]
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5c73af3b9187fa5365d7ea99474ea182d5f5ae86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="extending-servicehost-and-the-service-model-layer"></a><span data-ttu-id="4f57c-102">Extensión de ServiceHost y la capa de modelos de servicios</span><span class="sxs-lookup"><span data-stu-id="4f57c-102">Extending ServiceHost and the Service Model Layer</span></span>
<span data-ttu-id="4f57c-103">El nivel de modelo de servicio es responsable de extraer los mensajes entrantes de los canales subyacentes, de modo que los traduce en código de aplicación en las invocaciones de método y devuelve los resultados al agente de llamada.</span><span class="sxs-lookup"><span data-stu-id="4f57c-103">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span> <span data-ttu-id="4f57c-104">Las extensiones de modelo de servicio modifican o implementan el comportamiento de la comunicación o la ejecución y características implicadas en la funcionalidad de distribuidor o cliente, comportamientos personalizados, interceptación de mensajes y parámetros, y otra funcionalidad de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="4f57c-104">Service model extensions modify or implement execution or communication behavior and features involving client or dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f57c-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4f57c-105">In This Section</span></span>  
 [<span data-ttu-id="4f57c-106">Extensión de clientes</span><span class="sxs-lookup"><span data-stu-id="4f57c-106">Extending Clients</span></span>](../../../../docs/framework/wcf/extending/extending-clients.md)  
 <span data-ttu-id="4f57c-107">Describe las interfaces que pueden interceptar y modificar el tiempo de ejecución del cliente, así como las clases en las que puede insertar sus extensiones personalizadas en aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="4f57c-107">Describes the interfaces that can intercept and modify the client runtime, as well as the classes into which you can insert your custom extensions in client applications.</span></span> <span data-ttu-id="4f57c-108">Por ejemplo, puede realizar el registro de mensajes del cliente personalizado, realizar serialización del mensaje personalizada, etc.</span><span class="sxs-lookup"><span data-stu-id="4f57c-108">For example, you can perform custom client message logging, perform custom message serialization, and so on.</span></span>  
  
 [<span data-ttu-id="4f57c-109">Extensión de distribuidores</span><span class="sxs-lookup"><span data-stu-id="4f57c-109">Extending Dispatchers</span></span>](../../../../docs/framework/wcf/extending/extending-dispatchers.md)  
 <span data-ttu-id="4f57c-110">Describe las interfaces que pueden interceptar y modificar el tiempo de ejecución del servicio, así como las clases en las que puede insertar sus extensiones personalizadas en aplicaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="4f57c-110">Describes the interfaces that can intercept and modify the service runtime, as well as the classes into which you can insert your custom extensions in service applications.</span></span> <span data-ttu-id="4f57c-111">Por ejemplo, puede realizar el registro de servicio personalizado, la validación de mensajes del lado de servicio, distribución personalizada, etc.</span><span class="sxs-lookup"><span data-stu-id="4f57c-111">For example, you can perform custom service logging, service-side message validation, custom dispatching, and so on.</span></span>  
  
 [<span data-ttu-id="4f57c-112">Objetos extensibles</span><span class="sxs-lookup"><span data-stu-id="4f57c-112">Extensible Objects</span></span>](../../../../docs/framework/wcf/extending/extensible-objects.md)  
 <span data-ttu-id="4f57c-113">Describe los cinco objetos extensibles y el patrón <xref:System.ServiceModel.IExtensibleObject%601>.</span><span class="sxs-lookup"><span data-stu-id="4f57c-113">Describes the five extensible objects and the <xref:System.ServiceModel.IExtensibleObject%601> pattern.</span></span> <span data-ttu-id="4f57c-114">El patrón de objeto extensible se utiliza para extender clases de tiempo de ejecución existentes con nueva funcionalidad o para agregar un nuevo estado a un objeto.</span><span class="sxs-lookup"><span data-stu-id="4f57c-114">The extensible object pattern is used to either extend existing runtime classes with new functionality or to add new state to an object.</span></span> <span data-ttu-id="4f57c-115">Las extensiones, asociadas a uno de los objetos extensibles, permiten que los comportamientos en fases muy diferentes de procesamiento tengan acceso al estado compartido y funcionalidad adjuntos a un objeto extensible común al que pueden tener acceso.</span><span class="sxs-lookup"><span data-stu-id="4f57c-115">Extensions, attached to one of the extensible objects, enable behaviors at very different stages in processing to access shared state and functionality attached to a common extensible object that they can access.</span></span>  
  
 [<span data-ttu-id="4f57c-116">Configuración y extensión del tiempo de ejecución con comportamientos</span><span class="sxs-lookup"><span data-stu-id="4f57c-116">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 <span data-ttu-id="4f57c-117">Para cambiar los valores en o insertar extensiones en el tiempo de ejecución [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], utiliza comportamientos.</span><span class="sxs-lookup"><span data-stu-id="4f57c-117">To change settings on or insert extensions in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime, you use Behaviors.</span></span> <span data-ttu-id="4f57c-118">WCF incluye comportamientos implementados por el sistema para controlar la limitación de peticiones, la creación de instancias y muchos otros aspectos de servicios y operaciones.</span><span class="sxs-lookup"><span data-stu-id="4f57c-118">WCF includes system-implemented behaviors for controlling throttling, instancing, and many other aspects of services and operations.</span></span> <span data-ttu-id="4f57c-119">En esta sección se describe cómo crear sus propios comportamientos personalizados y cómo hacer que estén disponibles para el uso tanto a nivel de programación como utilizando archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="4f57c-119">This section describes how to create your own custom behaviors and how to make them available for use both programmatically and using configuration files.</span></span>  
  
 [<span data-ttu-id="4f57c-120">Extensión del hospedaje mediante ServiceHostFactory</span><span class="sxs-lookup"><span data-stu-id="4f57c-120">Extending Hosting Using ServiceHostFactory</span></span>](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 <span data-ttu-id="4f57c-121">Describe cómo extender <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>y utilizar las clases <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> para personalizar el entorno del host.</span><span class="sxs-lookup"><span data-stu-id="4f57c-121">Describes how to extend <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>, and use the <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> classes to customize the host environment.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4f57c-122">Referencia</span><span class="sxs-lookup"><span data-stu-id="4f57c-122">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4f57c-123">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4f57c-123">Related Sections</span></span>
