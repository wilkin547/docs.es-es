---
description: 'Más información acerca de: cliente y servicio de intranet no protegidos'
title: Cliente y servicio de intranet no protegidos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
ms.openlocfilehash: a03abc5b8eb0317c4d5d19347b3974d615570069
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704529"
---
# <a name="intranet-unsecured-client-and-service"></a><span data-ttu-id="2f06b-103">Cliente y servicio de intranet no protegidos</span><span class="sxs-lookup"><span data-stu-id="2f06b-103">Intranet Unsecured Client and Service</span></span>

<span data-ttu-id="2f06b-104">En la ilustración siguiente se muestra un servicio de Windows Communication Foundation simple (WCF) desarrollado para proporcionar información sobre una red privada segura a una aplicación WCF.</span><span class="sxs-lookup"><span data-stu-id="2f06b-104">The following illustration depicts a simple Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span> <span data-ttu-id="2f06b-105">No es necesaria la seguridad porque los datos son de poca importancia, se espera que la red sea intrínsecamente segura, o bien la seguridad la proporciona una capa por debajo de la infraestructura de WCF.</span><span class="sxs-lookup"><span data-stu-id="2f06b-105">Security is not required because the data is of low importance, the network is expected to be inherently secure, or security is provided by a layer below the WCF infrastructure.</span></span>  
  
 ![Escenario de servicio y cliente no seguro de la intranet.](./media/intranet-unsecured-client-and-service/unsecured-web-client-service.gif)  
  
|<span data-ttu-id="2f06b-107">Característica</span><span class="sxs-lookup"><span data-stu-id="2f06b-107">Characteristic</span></span>|<span data-ttu-id="2f06b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f06b-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="2f06b-109">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="2f06b-109">Security Mode</span></span>|<span data-ttu-id="2f06b-110">None</span><span class="sxs-lookup"><span data-stu-id="2f06b-110">None</span></span>|  
|<span data-ttu-id="2f06b-111">Transporte</span><span class="sxs-lookup"><span data-stu-id="2f06b-111">Transport</span></span>|<span data-ttu-id="2f06b-112">TCP</span><span class="sxs-lookup"><span data-stu-id="2f06b-112">TCP</span></span>|  
|<span data-ttu-id="2f06b-113">Enlace</span><span class="sxs-lookup"><span data-stu-id="2f06b-113">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
|<span data-ttu-id="2f06b-114">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="2f06b-114">Interoperability</span></span>|<span data-ttu-id="2f06b-115">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="2f06b-115">WCF only</span></span>|  
|<span data-ttu-id="2f06b-116">Authentication</span><span class="sxs-lookup"><span data-stu-id="2f06b-116">Authentication</span></span>|<span data-ttu-id="2f06b-117">Ninguno</span><span class="sxs-lookup"><span data-stu-id="2f06b-117">None</span></span>|  
|<span data-ttu-id="2f06b-118">Integridad</span><span class="sxs-lookup"><span data-stu-id="2f06b-118">Integrity</span></span>|<span data-ttu-id="2f06b-119">None</span><span class="sxs-lookup"><span data-stu-id="2f06b-119">None</span></span>|  
|<span data-ttu-id="2f06b-120">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="2f06b-120">Confidentiality</span></span>|<span data-ttu-id="2f06b-121">None</span><span class="sxs-lookup"><span data-stu-id="2f06b-121">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="2f06b-122">Servicio</span><span class="sxs-lookup"><span data-stu-id="2f06b-122">Service</span></span>  

 <span data-ttu-id="2f06b-123">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="2f06b-123">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="2f06b-124">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2f06b-124">Do one of the following:</span></span>  
  
- <span data-ttu-id="2f06b-125">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="2f06b-125">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="2f06b-126">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2f06b-126">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2f06b-127">Código</span><span class="sxs-lookup"><span data-stu-id="2f06b-127">Code</span></span>  

 <span data-ttu-id="2f06b-128">El siguiente código muestra cómo crear un extremo sin seguridad:</span><span class="sxs-lookup"><span data-stu-id="2f06b-128">The following code shows how to create an endpoint with no security:</span></span>  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="2f06b-129">Configuración</span><span class="sxs-lookup"><span data-stu-id="2f06b-129">Configuration</span></span>  

 <span data-ttu-id="2f06b-130">El código siguiente establece el mismo extremo utilizando la configuración.</span><span class="sxs-lookup"><span data-stu-id="2f06b-130">The following code sets up the same endpoint using configuration:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="2f06b-131">Cliente</span><span class="sxs-lookup"><span data-stu-id="2f06b-131">Client</span></span>  

 <span data-ttu-id="2f06b-132">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="2f06b-132">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="2f06b-133">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2f06b-133">Do one of the following:</span></span>  
  
- <span data-ttu-id="2f06b-134">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="2f06b-134">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="2f06b-135">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2f06b-135">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="2f06b-136">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="2f06b-136">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="2f06b-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2f06b-137">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="2f06b-138">Código</span><span class="sxs-lookup"><span data-stu-id="2f06b-138">Code</span></span>  

 <span data-ttu-id="2f06b-139">En el código siguiente se muestra un cliente de WCF básico que tiene acceso a un punto de conexión no seguro mediante el protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="2f06b-139">The following code shows a basic WCF client that accesses an unsecured endpoint using the TCP protocol.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="2f06b-140">Configuración</span><span class="sxs-lookup"><span data-stu-id="2f06b-140">Configuration</span></span>  

 <span data-ttu-id="2f06b-141">El código de configuración siguiente se aplica al cliente:</span><span class="sxs-lookup"><span data-stu-id="2f06b-141">The following configuration code applies to the client:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2f06b-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f06b-142">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- [<span data-ttu-id="2f06b-143">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="2f06b-143">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="2f06b-144">[Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="2f06b-144">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
