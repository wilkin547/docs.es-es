---
title: "Utilización de ServiceThrottlingBehavior para controlar el rendimiento de los servicios WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: behavior [WCF], service performance
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ead2990285f10400cfae11c21bce76a5b6c362f0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="using-servicethrottlingbehavior-to-control-wcf-service-performance"></a><span data-ttu-id="6866c-102">Utilización de ServiceThrottlingBehavior para controlar el rendimiento de los servicios WCF</span><span class="sxs-lookup"><span data-stu-id="6866c-102">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>
<span data-ttu-id="6866c-103">La clase <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> expone las propiedades que pueden utilizarse para limitar cuántas instancias o sesiones se crean en el nivel de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6866c-103">The <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> class exposes properties that you can use to limit how many instances or sessions are created at the application level.</span></span> <span data-ttu-id="6866c-104">Con este comportamiento, se precisa el rendimiento de su aplicación [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6866c-104">Using this behavior, you can fine-tune the performance of your [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application.</span></span>  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a><span data-ttu-id="6866c-105">Control de las instancias del servicio y las llamadas simultáneas</span><span class="sxs-lookup"><span data-stu-id="6866c-105">Controlling Service Instances and Concurrent Calls</span></span>  
 <span data-ttu-id="6866c-106">Utilice la propiedad <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> para especificar el número máximo de mensajes que se procesan activamente en una clase <xref:System.ServiceModel.ServiceHost>, y la propiedad <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> para especificar el número máximo de objetos <xref:System.ServiceModel.InstanceContext> del servicio.</span><span class="sxs-lookup"><span data-stu-id="6866c-106">Use the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> property to specify the maximum number of messages actively processing across a <xref:System.ServiceModel.ServiceHost> class, and the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> property to specify the maximum number of <xref:System.ServiceModel.InstanceContext> objects in the service.</span></span>  
  
 <span data-ttu-id="6866c-107">Carga debido a determinar los valores de estas propiedades normalmente tiene lugar después de ejecutar la aplicación con la experiencia real, la configuración para el <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> propiedades normalmente se especifica en un archivo de configuración de aplicación mediante el [ \<serviceThrottling >](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="6866c-107">Because determining the settings for these properties usually takes place after real-world experience running the application against loads, the settings for the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> properties is typically specified in an application configuration file using the [\<serviceThrottling>](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) element.</span></span>  
  
 <span data-ttu-id="6866c-108">El siguiente ejemplo de código muestra el uso de la clase <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> de un archivo de configuración de la aplicación que establece el valor 1 en <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, y las propiedades <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>, como ejemplo banal.</span><span class="sxs-lookup"><span data-stu-id="6866c-108">The following code example shows the use of the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> class from an application configuration file that sets the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, and <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> properties to 1 as a trivial example.</span></span> <span data-ttu-id="6866c-109">La experiencia real determina los valores óptimos para cualquier aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="6866c-109">Real-world experience determines the optimal settings for any particular application.</span></span>  
  
 [!code-xml[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  
  
 <span data-ttu-id="6866c-110">El comportamiento de tiempo de ejecución exacto depende en los valores de <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> y las propiedades <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>, que controlan cuántos mensajes pueden ejecutarse al mismo tiempo en una operación, y las duraciones del servicio <xref:System.ServiceModel.InstanceContext> en relación a las sesiones del canal de entrada, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6866c-110">The exact run-time behavior depends upon the values of the <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> and <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> properties, which control how many messages can execute inside an operation at once and the lifetimes of the service <xref:System.ServiceModel.InstanceContext> relative to incoming channel sessions, respectively.</span></span>  
  
 <span data-ttu-id="6866c-111">Para obtener información detallada, vea <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, y <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.</span><span class="sxs-lookup"><span data-stu-id="6866c-111">For details, see <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, and <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6866c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6866c-112">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>  
 <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>
