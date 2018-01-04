---
title: Cliente y servicio de intranet no protegidos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
caps.latest.revision: "20"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 0cfd98d401921c47bd85f8d4089e3efb437ca6b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="intranet-unsecured-client-and-service"></a><span data-ttu-id="00cb4-102">Cliente y servicio de intranet no protegidos</span><span class="sxs-lookup"><span data-stu-id="00cb4-102">Intranet Unsecured Client and Service</span></span>
<span data-ttu-id="00cb4-103">La ilustración siguiente describe un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] simple desarrollado para proporcionar información sobre una red privada segura a una aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00cb4-103">The following illustration depicts a simple [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service developed to provide information on a secure private network to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="00cb4-104">No se requiere seguridad porque los datos son de poca importancia, se supone que la red es intrínsecamente segura, o que la seguridad la proporciona una capa situada por debajo de la infraestructura [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00cb4-104">Security is not required because the data is of low importance, the network is expected to be inherently secure, or security is provided by a layer below the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure.</span></span>  
  
 <span data-ttu-id="00cb4-105">![Escenario de servicio y cliente de intranet segura](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")</span><span class="sxs-lookup"><span data-stu-id="00cb4-105">![Intranet unsecured client and service scenario](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")</span></span>  
  
|<span data-ttu-id="00cb4-106">Característica</span><span class="sxs-lookup"><span data-stu-id="00cb4-106">Characteristic</span></span>|<span data-ttu-id="00cb4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="00cb4-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="00cb4-108">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="00cb4-108">Security Mode</span></span>|<span data-ttu-id="00cb4-109">Ninguna</span><span class="sxs-lookup"><span data-stu-id="00cb4-109">None</span></span>|  
|<span data-ttu-id="00cb4-110">Transporte</span><span class="sxs-lookup"><span data-stu-id="00cb4-110">Transport</span></span>|<span data-ttu-id="00cb4-111">TCP</span><span class="sxs-lookup"><span data-stu-id="00cb4-111">TCP</span></span>|  
|<span data-ttu-id="00cb4-112">Enlaces</span><span class="sxs-lookup"><span data-stu-id="00cb4-112">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
|<span data-ttu-id="00cb4-113">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="00cb4-113">Interoperability</span></span>|<span data-ttu-id="00cb4-114">Solo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00cb4-114">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] only</span></span>|  
|<span data-ttu-id="00cb4-115">Autenticación</span><span class="sxs-lookup"><span data-stu-id="00cb4-115">Authentication</span></span>|<span data-ttu-id="00cb4-116">Ninguna</span><span class="sxs-lookup"><span data-stu-id="00cb4-116">None</span></span>|  
|<span data-ttu-id="00cb4-117">Integridad</span><span class="sxs-lookup"><span data-stu-id="00cb4-117">Integrity</span></span>|<span data-ttu-id="00cb4-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="00cb4-118">None</span></span>|  
|<span data-ttu-id="00cb4-119">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="00cb4-119">Confidentiality</span></span>|<span data-ttu-id="00cb4-120">Ninguna</span><span class="sxs-lookup"><span data-stu-id="00cb4-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="00cb4-121">Servicio</span><span class="sxs-lookup"><span data-stu-id="00cb4-121">Service</span></span>  
 <span data-ttu-id="00cb4-122">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="00cb4-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="00cb4-123">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="00cb4-123">Do one of the following:</span></span>  
  
-   <span data-ttu-id="00cb4-124">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="00cb4-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="00cb4-125">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún extremo.</span><span class="sxs-lookup"><span data-stu-id="00cb4-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="00cb4-126">Código</span><span class="sxs-lookup"><span data-stu-id="00cb4-126">Code</span></span>  
 <span data-ttu-id="00cb4-127">El siguiente código muestra cómo crear un extremo sin seguridad:</span><span class="sxs-lookup"><span data-stu-id="00cb4-127">The following code shows how to create an endpoint with no security:</span></span>  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="00cb4-128">Configuración</span><span class="sxs-lookup"><span data-stu-id="00cb4-128">Configuration</span></span>  
 <span data-ttu-id="00cb4-129">El código siguiente establece el mismo extremo utilizando la configuración.</span><span class="sxs-lookup"><span data-stu-id="00cb4-129">The following code sets up the same endpoint using configuration:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration=""   
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"   
                  binding="netTcpBinding"  
                  bindingConfiguration="tcp_Unsecured"   
                  name="netTcp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="tcp_Unsecured">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="00cb4-130">Cliente</span><span class="sxs-lookup"><span data-stu-id="00cb4-130">Client</span></span>  
 <span data-ttu-id="00cb4-131">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="00cb4-131">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="00cb4-132">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="00cb4-132">Do one of the following:</span></span>  
  
-   <span data-ttu-id="00cb4-133">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="00cb4-133">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="00cb4-134">Cree un cliente que no defina direcciones de extremo.</span><span class="sxs-lookup"><span data-stu-id="00cb4-134">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="00cb4-135">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="00cb4-135">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="00cb4-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="00cb4-136">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="00cb4-137">Código</span><span class="sxs-lookup"><span data-stu-id="00cb4-137">Code</span></span>  
 <span data-ttu-id="00cb4-138">El código siguiente muestra un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] básico que puede acceder a un extremo sin protección mediante el protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="00cb4-138">The following code shows a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that accesses an unsecured endpoint using the TCP protocol.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="00cb4-139">Configuración</span><span class="sxs-lookup"><span data-stu-id="00cb4-139">Configuration</span></span>  
 <span data-ttu-id="00cb4-140">El código de configuración siguiente se aplica al cliente:</span><span class="sxs-lookup"><span data-stu-id="00cb4-140">The following configuration code applies to the client:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator "  
                binding="netTcpBinding"   
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"   
                name="NetTcpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="00cb4-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="00cb4-141">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpBinding>  
 [<span data-ttu-id="00cb4-142">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="00cb4-142">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="00cb4-143">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="00cb4-143">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
