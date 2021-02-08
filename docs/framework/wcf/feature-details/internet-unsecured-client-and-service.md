---
description: 'Más información acerca de: servicio y cliente sin protección de Internet'
title: Cliente y servicio de Internet no protegidos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
ms.openlocfilehash: 8b402b276c80b2e1c148de0837d8644aad7a2d4a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802780"
---
# <a name="internet-unsecured-client-and-service"></a><span data-ttu-id="9c595-103">Cliente y servicio de Internet no protegidos</span><span class="sxs-lookup"><span data-stu-id="9c595-103">Internet Unsecured Client and Service</span></span>

<span data-ttu-id="9c595-104">En la ilustración siguiente se muestra un ejemplo de un cliente y un servicio de Windows Communication Foundation (WCF) públicos y no seguros:</span><span class="sxs-lookup"><span data-stu-id="9c595-104">The following illustration shows an example of a public, unsecured Windows Communication Foundation (WCF) client and service:</span></span>  
  
 ![Captura de pantalla que muestra un escenario de Internet no seguro](./media/internet-unsecured-client-and-service/public-unsecured-internet.gif)  
  
|<span data-ttu-id="9c595-106">Característica</span><span class="sxs-lookup"><span data-stu-id="9c595-106">Characteristic</span></span>|<span data-ttu-id="9c595-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c595-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="9c595-108">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="9c595-108">Security Mode</span></span>|<span data-ttu-id="9c595-109">None</span><span class="sxs-lookup"><span data-stu-id="9c595-109">None</span></span>|  
|<span data-ttu-id="9c595-110">Transporte</span><span class="sxs-lookup"><span data-stu-id="9c595-110">Transport</span></span>|<span data-ttu-id="9c595-111">HTTP</span><span class="sxs-lookup"><span data-stu-id="9c595-111">HTTP</span></span>|  
|<span data-ttu-id="9c595-112">Enlace</span><span class="sxs-lookup"><span data-stu-id="9c595-112">Binding</span></span>|<span data-ttu-id="9c595-113"><xref:System.ServiceModel.BasicHttpBinding> en el código o [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) en el elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="9c595-113"><xref:System.ServiceModel.BasicHttpBinding> in code, or the [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) element in configuration.</span></span>|  
|<span data-ttu-id="9c595-114">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="9c595-114">Interoperability</span></span>|<span data-ttu-id="9c595-115">Con clientes de servicios Web existentes y servicios</span><span class="sxs-lookup"><span data-stu-id="9c595-115">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="9c595-116">Authentication</span><span class="sxs-lookup"><span data-stu-id="9c595-116">Authentication</span></span>|<span data-ttu-id="9c595-117">Ninguno</span><span class="sxs-lookup"><span data-stu-id="9c595-117">None</span></span>|  
|<span data-ttu-id="9c595-118">Integridad</span><span class="sxs-lookup"><span data-stu-id="9c595-118">Integrity</span></span>|<span data-ttu-id="9c595-119">None</span><span class="sxs-lookup"><span data-stu-id="9c595-119">None</span></span>|  
|<span data-ttu-id="9c595-120">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="9c595-120">Confidentiality</span></span>|<span data-ttu-id="9c595-121">None</span><span class="sxs-lookup"><span data-stu-id="9c595-121">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="9c595-122">Servicio</span><span class="sxs-lookup"><span data-stu-id="9c595-122">Service</span></span>  

 <span data-ttu-id="9c595-123">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="9c595-123">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="9c595-124">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="9c595-124">Do one of the following:</span></span>  
  
- <span data-ttu-id="9c595-125">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="9c595-125">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="9c595-126">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9c595-126">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9c595-127">Código</span><span class="sxs-lookup"><span data-stu-id="9c595-127">Code</span></span>  

 <span data-ttu-id="9c595-128">El siguiente código muestra cómo crear punto de conexión sin seguridad.</span><span class="sxs-lookup"><span data-stu-id="9c595-128">The following code shows how to create an endpoint with no security.</span></span> <span data-ttu-id="9c595-129">De forma predeterminada, <xref:System.ServiceModel.BasicHttpBinding> tiene el modo de seguridad establecido en <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span><span class="sxs-lookup"><span data-stu-id="9c595-129">By default, the <xref:System.ServiceModel.BasicHttpBinding> has the security mode set to <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span></span>  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a><span data-ttu-id="9c595-130">Configuración de servicio</span><span class="sxs-lookup"><span data-stu-id="9c595-130">Service Configuration</span></span>  

 <span data-ttu-id="9c595-131">El código siguiente configura el mismo extremo mediante la configuración.</span><span class="sxs-lookup"><span data-stu-id="9c595-131">The following code sets up the same endpoint using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"
                  binding="basicHttpBinding"  
                  bindingConfiguration="Basic_Unsecured"
                  name="BasicHttp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="Basic_Unsecured" />  
      </basicHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="9c595-132">Cliente</span><span class="sxs-lookup"><span data-stu-id="9c595-132">Client</span></span>  

 <span data-ttu-id="9c595-133">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="9c595-133">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="9c595-134">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="9c595-134">Do one of the following:</span></span>  
  
- <span data-ttu-id="9c595-135">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="9c595-135">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="9c595-136">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9c595-136">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="9c595-137">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="9c595-137">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="9c595-138">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9c595-138">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="9c595-139">Código</span><span class="sxs-lookup"><span data-stu-id="9c595-139">Code</span></span>  

 <span data-ttu-id="9c595-140">En el código siguiente se muestra un cliente de WCF básico que tiene acceso a un punto de conexión no seguro.</span><span class="sxs-lookup"><span data-stu-id="9c595-140">The following code shows a basic WCF client that accesses an unsecured endpoint.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a><span data-ttu-id="9c595-141">Configuración del cliente</span><span class="sxs-lookup"><span data-stu-id="9c595-141">Client Configuration</span></span>  

 <span data-ttu-id="9c595-142">El siguiente código configura el cliente.</span><span class="sxs-lookup"><span data-stu-id="9c595-142">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="BasicHttpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator/Unsecured"  
          binding="basicHttpBinding"
          bindingConfiguration="BasicHttpBinding_ICalculator"  
          contract="ICalculator"
          name="BasicHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c595-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c595-143">See also</span></span>

- [<span data-ttu-id="9c595-144">Escenarios de seguridad comunes</span><span class="sxs-lookup"><span data-stu-id="9c595-144">Common Security Scenarios</span></span>](common-security-scenarios.md)
- [<span data-ttu-id="9c595-145">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="9c595-145">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="9c595-146">[Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="9c595-146">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
