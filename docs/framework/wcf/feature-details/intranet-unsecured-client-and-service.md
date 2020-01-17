---
title: Cliente y servicio de intranet no protegidos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
ms.openlocfilehash: 1ffd0421195b0339ad966b661c229e5a5ebb94ec
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212098"
---
# <a name="intranet-unsecured-client-and-service"></a><span data-ttu-id="0c267-102">Cliente y servicio de intranet no protegidos</span><span class="sxs-lookup"><span data-stu-id="0c267-102">Intranet Unsecured Client and Service</span></span>
<span data-ttu-id="0c267-103">En la ilustración siguiente se muestra un servicio de Windows Communication Foundation simple (WCF) desarrollado para proporcionar información sobre una red privada segura a una aplicación WCF.</span><span class="sxs-lookup"><span data-stu-id="0c267-103">The following illustration depicts a simple Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span> <span data-ttu-id="0c267-104">No es necesaria la seguridad porque los datos son de poca importancia, se espera que la red sea intrínsecamente segura, o bien la seguridad la proporciona una capa por debajo de la infraestructura de WCF.</span><span class="sxs-lookup"><span data-stu-id="0c267-104">Security is not required because the data is of low importance, the network is expected to be inherently secure, or security is provided by a layer below the WCF infrastructure.</span></span>  
  
 ![Escenario de servicio y cliente no seguro de la intranet.](./media/intranet-unsecured-client-and-service/unsecured-web-client-service.gif)  
  
|<span data-ttu-id="0c267-106">Característica</span><span class="sxs-lookup"><span data-stu-id="0c267-106">Characteristic</span></span>|<span data-ttu-id="0c267-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c267-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0c267-108">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="0c267-108">Security Mode</span></span>|<span data-ttu-id="0c267-109">Ninguno</span><span class="sxs-lookup"><span data-stu-id="0c267-109">None</span></span>|  
|<span data-ttu-id="0c267-110">Transport</span><span class="sxs-lookup"><span data-stu-id="0c267-110">Transport</span></span>|<span data-ttu-id="0c267-111">TCP</span><span class="sxs-lookup"><span data-stu-id="0c267-111">TCP</span></span>|  
|<span data-ttu-id="0c267-112">Enlace</span><span class="sxs-lookup"><span data-stu-id="0c267-112">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
|<span data-ttu-id="0c267-113">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="0c267-113">Interoperability</span></span>|<span data-ttu-id="0c267-114">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="0c267-114">WCF only</span></span>|  
|<span data-ttu-id="0c267-115">Autenticación</span><span class="sxs-lookup"><span data-stu-id="0c267-115">Authentication</span></span>|<span data-ttu-id="0c267-116">Ninguno</span><span class="sxs-lookup"><span data-stu-id="0c267-116">None</span></span>|  
|<span data-ttu-id="0c267-117">Integridad</span><span class="sxs-lookup"><span data-stu-id="0c267-117">Integrity</span></span>|<span data-ttu-id="0c267-118">Ninguno</span><span class="sxs-lookup"><span data-stu-id="0c267-118">None</span></span>|  
|<span data-ttu-id="0c267-119">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="0c267-119">Confidentiality</span></span>|<span data-ttu-id="0c267-120">Ninguno</span><span class="sxs-lookup"><span data-stu-id="0c267-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="0c267-121">Servicio</span><span class="sxs-lookup"><span data-stu-id="0c267-121">Service</span></span>  
 <span data-ttu-id="0c267-122">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="0c267-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="0c267-123">Siga uno de los procedimientos que se describen a continuación:</span><span class="sxs-lookup"><span data-stu-id="0c267-123">Do one of the following:</span></span>  
  
- <span data-ttu-id="0c267-124">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="0c267-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="0c267-125">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0c267-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0c267-126">Código</span><span class="sxs-lookup"><span data-stu-id="0c267-126">Code</span></span>  
 <span data-ttu-id="0c267-127">El siguiente código muestra cómo crear un extremo sin seguridad:</span><span class="sxs-lookup"><span data-stu-id="0c267-127">The following code shows how to create an endpoint with no security:</span></span>  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="0c267-128">Configuración de</span><span class="sxs-lookup"><span data-stu-id="0c267-128">Configuration</span></span>  
 <span data-ttu-id="0c267-129">El código siguiente establece el mismo extremo utilizando la configuración.</span><span class="sxs-lookup"><span data-stu-id="0c267-129">The following code sets up the same endpoint using configuration:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="0c267-130">Client</span><span class="sxs-lookup"><span data-stu-id="0c267-130">Client</span></span>  
 <span data-ttu-id="0c267-131">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="0c267-131">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="0c267-132">Siga uno de los procedimientos que se describen a continuación:</span><span class="sxs-lookup"><span data-stu-id="0c267-132">Do one of the following:</span></span>  
  
- <span data-ttu-id="0c267-133">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="0c267-133">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="0c267-134">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0c267-134">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="0c267-135">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="0c267-135">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="0c267-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0c267-136">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="0c267-137">Código</span><span class="sxs-lookup"><span data-stu-id="0c267-137">Code</span></span>  
 <span data-ttu-id="0c267-138">En el código siguiente se muestra un cliente de WCF básico que tiene acceso a un punto de conexión no seguro mediante el protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="0c267-138">The following code shows a basic WCF client that accesses an unsecured endpoint using the TCP protocol.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="0c267-139">Configuración de</span><span class="sxs-lookup"><span data-stu-id="0c267-139">Configuration</span></span>  
 <span data-ttu-id="0c267-140">El código de configuración siguiente se aplica al cliente:</span><span class="sxs-lookup"><span data-stu-id="0c267-140">The following configuration code applies to the client:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0c267-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c267-141">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- [<span data-ttu-id="0c267-142">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="0c267-142">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="0c267-143">[Modelo de seguridad para Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="0c267-143">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
