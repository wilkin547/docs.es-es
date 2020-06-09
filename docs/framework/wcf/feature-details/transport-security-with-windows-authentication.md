---
title: Seguridad del transporte con la autenticación de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: 6703da4f97cba38ee0dc334d3010ca509d1fb3ef
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598702"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="8a641-102">Seguridad del transporte con la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="8a641-102">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="8a641-103">En el siguiente escenario se muestra un servicio y un cliente de Windows Communication Foundation (WCF) protegidos por la seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="8a641-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="8a641-104">Para obtener más información acerca de la programación, consulte [Cómo: proteger un servicio con credenciales de Windows](../how-to-secure-a-service-with-windows-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="8a641-104">For more information about programming, see [How to: Secure a Service with Windows Credentials](../how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="8a641-105">Un Servicio Web de la intranet muestra la información de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="8a641-105">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="8a641-106">El cliente es una aplicación de Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8a641-106">The client is a Windows Form application.</span></span> <span data-ttu-id="8a641-107">La aplicación se implementa en un dominio con un controlador Kerberos que protege el dominio.</span><span class="sxs-lookup"><span data-stu-id="8a641-107">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 ![Seguridad del transporte con la autenticación de Windows](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|<span data-ttu-id="8a641-109">Característica</span><span class="sxs-lookup"><span data-stu-id="8a641-109">Characteristic</span></span>|<span data-ttu-id="8a641-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a641-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="8a641-111">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="8a641-111">Security Mode</span></span>|<span data-ttu-id="8a641-112">Transporte</span><span class="sxs-lookup"><span data-stu-id="8a641-112">Transport</span></span>|  
|<span data-ttu-id="8a641-113">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="8a641-113">Interoperability</span></span>|<span data-ttu-id="8a641-114">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="8a641-114">WCF only</span></span>|  
|<span data-ttu-id="8a641-115">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="8a641-115">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="8a641-116">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="8a641-116">Authentication (Client)</span></span>|<span data-ttu-id="8a641-117">Sí (al utilizar la autenticación integrada de Windows)</span><span class="sxs-lookup"><span data-stu-id="8a641-117">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="8a641-118">Sí (al utilizar la autenticación integrada de Windows)</span><span class="sxs-lookup"><span data-stu-id="8a641-118">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="8a641-119">Integridad</span><span class="sxs-lookup"><span data-stu-id="8a641-119">Integrity</span></span>|<span data-ttu-id="8a641-120">Sí</span><span class="sxs-lookup"><span data-stu-id="8a641-120">Yes</span></span>|  
|<span data-ttu-id="8a641-121">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="8a641-121">Confidentiality</span></span>|<span data-ttu-id="8a641-122">Sí</span><span class="sxs-lookup"><span data-stu-id="8a641-122">Yes</span></span>|  
|<span data-ttu-id="8a641-123">Transporte</span><span class="sxs-lookup"><span data-stu-id="8a641-123">Transport</span></span>|<span data-ttu-id="8a641-124">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="8a641-124">NET.TCP</span></span>|  
|<span data-ttu-id="8a641-125">Enlace</span><span class="sxs-lookup"><span data-stu-id="8a641-125">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="8a641-126">web de Office</span><span class="sxs-lookup"><span data-stu-id="8a641-126">Service</span></span>  
 <span data-ttu-id="8a641-127">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="8a641-127">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="8a641-128">Lleve a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8a641-128">Do one of the following:</span></span>  
  
- <span data-ttu-id="8a641-129">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="8a641-129">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="8a641-130">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8a641-130">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="8a641-131">Código</span><span class="sxs-lookup"><span data-stu-id="8a641-131">Code</span></span>  
 <span data-ttu-id="8a641-132">El código siguiente muestra cómo crear un extremo de servicio que utilice la seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="8a641-132">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="8a641-133">Configuración</span><span class="sxs-lookup"><span data-stu-id="8a641-133">Configuration</span></span>  
 <span data-ttu-id="8a641-134">Se puede usar la configuración siguiente en lugar del código para configurar el punto de conexión de servicio:</span><span class="sxs-lookup"><span data-stu-id="8a641-134">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="8a641-135">Cliente</span><span class="sxs-lookup"><span data-stu-id="8a641-135">Client</span></span>  
 <span data-ttu-id="8a641-136">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="8a641-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="8a641-137">Lleve a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8a641-137">Do one of the following:</span></span>  
  
- <span data-ttu-id="8a641-138">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="8a641-138">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="8a641-139">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8a641-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="8a641-140">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="8a641-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="8a641-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8a641-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="8a641-142">Código</span><span class="sxs-lookup"><span data-stu-id="8a641-142">Code</span></span>  
 <span data-ttu-id="8a641-143">El siguiente código crea el cliente.</span><span class="sxs-lookup"><span data-stu-id="8a641-143">The following code creates the client.</span></span> <span data-ttu-id="8a641-144">El enlace se configura para utilizar la seguridad del modo de transporte, con el transporte TCP, con el tipo de credencial de cliente establecido en Windows.</span><span class="sxs-lookup"><span data-stu-id="8a641-144">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="8a641-145">Configuración</span><span class="sxs-lookup"><span data-stu-id="8a641-145">Configuration</span></span>  
 <span data-ttu-id="8a641-146">La configuración siguiente se puede utilizar en lugar del código para crear el cliente.</span><span class="sxs-lookup"><span data-stu-id="8a641-146">The following configuration can be used instead of the code to create the client.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8a641-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a641-147">See also</span></span>

- [<span data-ttu-id="8a641-148">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="8a641-148">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="8a641-149">Procedimiento para proteger un servicio con credenciales de Windows</span><span class="sxs-lookup"><span data-stu-id="8a641-149">How to: Secure a Service with Windows Credentials</span></span>](../how-to-secure-a-service-with-windows-credentials.md)
- <span data-ttu-id="8a641-150">[Modelo de seguridad para Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="8a641-150">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
