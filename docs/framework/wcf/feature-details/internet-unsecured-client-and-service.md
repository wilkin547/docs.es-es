---
title: Cliente y servicio de Internet no protegidos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
ms.openlocfilehash: 4a84b32664c16dad48dd415e430134c5fb98303a
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76211926"
---
# <a name="internet-unsecured-client-and-service"></a><span data-ttu-id="ac380-102">Cliente y servicio de Internet no protegidos</span><span class="sxs-lookup"><span data-stu-id="ac380-102">Internet Unsecured Client and Service</span></span>
<span data-ttu-id="ac380-103">En la ilustración siguiente se muestra un ejemplo de un cliente y un servicio de Windows Communication Foundation (WCF) públicos y no seguros:</span><span class="sxs-lookup"><span data-stu-id="ac380-103">The following illustration shows an example of a public, unsecured Windows Communication Foundation (WCF) client and service:</span></span>  
  
 ![Captura de pantalla que muestra un escenario de Internet no seguro](./media/internet-unsecured-client-and-service/public-unsecured-internet.gif)  
  
|<span data-ttu-id="ac380-105">Característica</span><span class="sxs-lookup"><span data-stu-id="ac380-105">Characteristic</span></span>|<span data-ttu-id="ac380-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac380-106">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="ac380-107">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="ac380-107">Security Mode</span></span>|<span data-ttu-id="ac380-108">Ninguno</span><span class="sxs-lookup"><span data-stu-id="ac380-108">None</span></span>|  
|<span data-ttu-id="ac380-109">Transport</span><span class="sxs-lookup"><span data-stu-id="ac380-109">Transport</span></span>|<span data-ttu-id="ac380-110">HTTP</span><span class="sxs-lookup"><span data-stu-id="ac380-110">HTTP</span></span>|  
|<span data-ttu-id="ac380-111">Enlace</span><span class="sxs-lookup"><span data-stu-id="ac380-111">Binding</span></span>|<span data-ttu-id="ac380-112"><xref:System.ServiceModel.BasicHttpBinding> en el código o en el elemento de [\<basicHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) en la configuración.</span><span class="sxs-lookup"><span data-stu-id="ac380-112"><xref:System.ServiceModel.BasicHttpBinding> in code, or the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element in configuration.</span></span>|  
|<span data-ttu-id="ac380-113">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="ac380-113">Interoperability</span></span>|<span data-ttu-id="ac380-114">Con clientes de servicios Web existentes y servicios</span><span class="sxs-lookup"><span data-stu-id="ac380-114">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="ac380-115">Autenticación</span><span class="sxs-lookup"><span data-stu-id="ac380-115">Authentication</span></span>|<span data-ttu-id="ac380-116">Ninguno</span><span class="sxs-lookup"><span data-stu-id="ac380-116">None</span></span>|  
|<span data-ttu-id="ac380-117">Integridad</span><span class="sxs-lookup"><span data-stu-id="ac380-117">Integrity</span></span>|<span data-ttu-id="ac380-118">Ninguno</span><span class="sxs-lookup"><span data-stu-id="ac380-118">None</span></span>|  
|<span data-ttu-id="ac380-119">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="ac380-119">Confidentiality</span></span>|<span data-ttu-id="ac380-120">Ninguno</span><span class="sxs-lookup"><span data-stu-id="ac380-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="ac380-121">Servicio</span><span class="sxs-lookup"><span data-stu-id="ac380-121">Service</span></span>  
 <span data-ttu-id="ac380-122">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="ac380-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="ac380-123">Siga uno de los procedimientos que se describen a continuación:</span><span class="sxs-lookup"><span data-stu-id="ac380-123">Do one of the following:</span></span>  
  
- <span data-ttu-id="ac380-124">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="ac380-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="ac380-125">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ac380-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ac380-126">Código</span><span class="sxs-lookup"><span data-stu-id="ac380-126">Code</span></span>  
 <span data-ttu-id="ac380-127">El siguiente código muestra cómo crear punto de conexión sin seguridad.</span><span class="sxs-lookup"><span data-stu-id="ac380-127">The following code shows how to create an endpoint with no security.</span></span> <span data-ttu-id="ac380-128">De forma predeterminada, <xref:System.ServiceModel.BasicHttpBinding> tiene el modo de seguridad establecido en <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span><span class="sxs-lookup"><span data-stu-id="ac380-128">By default, the <xref:System.ServiceModel.BasicHttpBinding> has the security mode set to <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span></span>  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a><span data-ttu-id="ac380-129">Configuración del servicio</span><span class="sxs-lookup"><span data-stu-id="ac380-129">Service Configuration</span></span>  
 <span data-ttu-id="ac380-130">El código siguiente configura el mismo extremo mediante la configuración.</span><span class="sxs-lookup"><span data-stu-id="ac380-130">The following code sets up the same endpoint using configuration.</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="ac380-131">Client</span><span class="sxs-lookup"><span data-stu-id="ac380-131">Client</span></span>  
 <span data-ttu-id="ac380-132">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="ac380-132">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="ac380-133">Siga uno de los procedimientos que se describen a continuación:</span><span class="sxs-lookup"><span data-stu-id="ac380-133">Do one of the following:</span></span>  
  
- <span data-ttu-id="ac380-134">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="ac380-134">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="ac380-135">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ac380-135">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="ac380-136">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="ac380-136">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="ac380-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ac380-137">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="ac380-138">Código</span><span class="sxs-lookup"><span data-stu-id="ac380-138">Code</span></span>  
 <span data-ttu-id="ac380-139">En el código siguiente se muestra un cliente de WCF básico que tiene acceso a un punto de conexión no seguro.</span><span class="sxs-lookup"><span data-stu-id="ac380-139">The following code shows a basic WCF client that accesses an unsecured endpoint.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a><span data-ttu-id="ac380-140">Configuración del cliente</span><span class="sxs-lookup"><span data-stu-id="ac380-140">Client Configuration</span></span>  
 <span data-ttu-id="ac380-141">El siguiente código configura el cliente.</span><span class="sxs-lookup"><span data-stu-id="ac380-141">The following code configures the client.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ac380-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac380-142">See also</span></span>

- [<span data-ttu-id="ac380-143">Escenarios de seguridad comunes</span><span class="sxs-lookup"><span data-stu-id="ac380-143">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)
- [<span data-ttu-id="ac380-144">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="ac380-144">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="ac380-145">[Modelo de seguridad para Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="ac380-145">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
