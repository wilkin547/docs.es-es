---
title: Seguridad del transporte con la autenticación de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: d335cd47de68dccdbb6af7f402d1182fcd811a7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184316"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="df765-102">Seguridad del transporte con la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="df765-102">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="df765-103">En el escenario siguiente se muestra un cliente de Windows Communication Foundation (WCF) y un servicio protegido por la seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="df765-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="df765-104">Para obtener más información acerca de la programación, vea [Cómo: proteger un servicio con credenciales](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md)de Windows .</span><span class="sxs-lookup"><span data-stu-id="df765-104">For more information about programming, see [How to: Secure a Service with Windows Credentials](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="df765-105">Un Servicio Web de la intranet muestra la información de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="df765-105">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="df765-106">El cliente es una aplicación de Windows Form.</span><span class="sxs-lookup"><span data-stu-id="df765-106">The client is a Windows Form application.</span></span> <span data-ttu-id="df765-107">La aplicación se implementa en un dominio con un controlador Kerberos que protege el dominio.</span><span class="sxs-lookup"><span data-stu-id="df765-107">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 ![Seguridad del transporte con la autenticación de Windows](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|<span data-ttu-id="df765-109">Característica</span><span class="sxs-lookup"><span data-stu-id="df765-109">Characteristic</span></span>|<span data-ttu-id="df765-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="df765-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="df765-111">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="df765-111">Security Mode</span></span>|<span data-ttu-id="df765-112">Transporte</span><span class="sxs-lookup"><span data-stu-id="df765-112">Transport</span></span>|  
|<span data-ttu-id="df765-113">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="df765-113">Interoperability</span></span>|<span data-ttu-id="df765-114">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="df765-114">WCF only</span></span>|  
|<span data-ttu-id="df765-115">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="df765-115">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="df765-116">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="df765-116">Authentication (Client)</span></span>|<span data-ttu-id="df765-117">Sí (al utilizar la autenticación integrada de Windows)</span><span class="sxs-lookup"><span data-stu-id="df765-117">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="df765-118">Sí (al utilizar la autenticación integrada de Windows)</span><span class="sxs-lookup"><span data-stu-id="df765-118">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="df765-119">Integridad</span><span class="sxs-lookup"><span data-stu-id="df765-119">Integrity</span></span>|<span data-ttu-id="df765-120">Sí</span><span class="sxs-lookup"><span data-stu-id="df765-120">Yes</span></span>|  
|<span data-ttu-id="df765-121">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="df765-121">Confidentiality</span></span>|<span data-ttu-id="df765-122">Sí</span><span class="sxs-lookup"><span data-stu-id="df765-122">Yes</span></span>|  
|<span data-ttu-id="df765-123">Transporte</span><span class="sxs-lookup"><span data-stu-id="df765-123">Transport</span></span>|<span data-ttu-id="df765-124">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="df765-124">NET.TCP</span></span>|  
|<span data-ttu-id="df765-125">Enlace</span><span class="sxs-lookup"><span data-stu-id="df765-125">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="df765-126">Servicio</span><span class="sxs-lookup"><span data-stu-id="df765-126">Service</span></span>  
 <span data-ttu-id="df765-127">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="df765-127">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="df765-128">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="df765-128">Do one of the following:</span></span>  
  
- <span data-ttu-id="df765-129">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="df765-129">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="df765-130">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="df765-130">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="df765-131">Código</span><span class="sxs-lookup"><span data-stu-id="df765-131">Code</span></span>  
 <span data-ttu-id="df765-132">El código siguiente muestra cómo crear un extremo de servicio que utilice la seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="df765-132">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="df765-133">Configuración</span><span class="sxs-lookup"><span data-stu-id="df765-133">Configuration</span></span>  
 <span data-ttu-id="df765-134">Se puede usar la configuración siguiente en lugar del código para configurar el punto de conexión de servicio:</span><span class="sxs-lookup"><span data-stu-id="df765-134">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"
                  binding="netTcpBinding"  
          bindingConfiguration="WindowsClientOverTcp"
                  name="WindowsClientOverTcp"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="WindowsClientOverTcp">  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="df765-135">Remoto</span><span class="sxs-lookup"><span data-stu-id="df765-135">Client</span></span>  
 <span data-ttu-id="df765-136">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="df765-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="df765-137">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="df765-137">Do one of the following:</span></span>  
  
- <span data-ttu-id="df765-138">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="df765-138">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="df765-139">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="df765-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="df765-140">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="df765-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="df765-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="df765-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="df765-142">Código</span><span class="sxs-lookup"><span data-stu-id="df765-142">Code</span></span>  
 <span data-ttu-id="df765-143">El siguiente código crea el cliente.</span><span class="sxs-lookup"><span data-stu-id="df765-143">The following code creates the client.</span></span> <span data-ttu-id="df765-144">El enlace se configura para utilizar la seguridad del modo de transporte, con el transporte TCP, con el tipo de credencial de cliente establecido en Windows.</span><span class="sxs-lookup"><span data-stu-id="df765-144">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="df765-145">Configuración</span><span class="sxs-lookup"><span data-stu-id="df765-145">Configuration</span></span>  
 <span data-ttu-id="df765-146">La configuración siguiente se puede utilizar en lugar del código para crear el cliente.</span><span class="sxs-lookup"><span data-stu-id="df765-146">The following configuration can be used instead of the code to create the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://localhost:8008/Calculator"
                binding="netTcpBinding"
                bindingConfiguration="NetTcpBinding_ICalculator"
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="df765-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df765-147">See also</span></span>

- [<span data-ttu-id="df765-148">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="df765-148">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="df765-149">Cómo proteger un servicio con credenciales de Windows</span><span class="sxs-lookup"><span data-stu-id="df765-149">How to: Secure a Service with Windows Credentials</span></span>](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md)
- <span data-ttu-id="df765-150">[Modelo de seguridad para Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="df765-150">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
