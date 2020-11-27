---
title: Seguridad del transporte con la autenticación de Windows
description: Revise este escenario, que muestra un cliente/servicio de WCF protegido por la seguridad de Windows. En este ejemplo, un servicio de intranet muestra información de recursos humanos.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: 47f5a2a3b2c8815e2ccb0cc4d4bf3c408f4992e2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251742"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="d17c3-104">Seguridad del transporte con la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="d17c3-104">Transport Security with Windows Authentication</span></span>

<span data-ttu-id="d17c3-105">En el siguiente escenario se muestra un servicio y un cliente de Windows Communication Foundation (WCF) protegidos por la seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="d17c3-105">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="d17c3-106">Para obtener más información acerca de la programación, consulte [Cómo: proteger un servicio con credenciales de Windows](../how-to-secure-a-service-with-windows-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="d17c3-106">For more information about programming, see [How to: Secure a Service with Windows Credentials](../how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="d17c3-107">Un Servicio Web de la intranet muestra la información de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="d17c3-107">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="d17c3-108">El cliente es una aplicación de Windows Form.</span><span class="sxs-lookup"><span data-stu-id="d17c3-108">The client is a Windows Form application.</span></span> <span data-ttu-id="d17c3-109">La aplicación se implementa en un dominio con un controlador Kerberos que protege el dominio.</span><span class="sxs-lookup"><span data-stu-id="d17c3-109">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 ![Seguridad del transporte con la autenticación de Windows](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|<span data-ttu-id="d17c3-111">Característica</span><span class="sxs-lookup"><span data-stu-id="d17c3-111">Characteristic</span></span>|<span data-ttu-id="d17c3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d17c3-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d17c3-113">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="d17c3-113">Security Mode</span></span>|<span data-ttu-id="d17c3-114">Transporte</span><span class="sxs-lookup"><span data-stu-id="d17c3-114">Transport</span></span>|  
|<span data-ttu-id="d17c3-115">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="d17c3-115">Interoperability</span></span>|<span data-ttu-id="d17c3-116">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="d17c3-116">WCF only</span></span>|  
|<span data-ttu-id="d17c3-117">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="d17c3-117">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="d17c3-118">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="d17c3-118">Authentication (Client)</span></span>|<span data-ttu-id="d17c3-119">Sí (al utilizar la autenticación integrada de Windows)</span><span class="sxs-lookup"><span data-stu-id="d17c3-119">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="d17c3-120">Sí (al utilizar la autenticación integrada de Windows)</span><span class="sxs-lookup"><span data-stu-id="d17c3-120">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="d17c3-121">Integridad</span><span class="sxs-lookup"><span data-stu-id="d17c3-121">Integrity</span></span>|<span data-ttu-id="d17c3-122">Yes</span><span class="sxs-lookup"><span data-stu-id="d17c3-122">Yes</span></span>|  
|<span data-ttu-id="d17c3-123">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="d17c3-123">Confidentiality</span></span>|<span data-ttu-id="d17c3-124">Sí</span><span class="sxs-lookup"><span data-stu-id="d17c3-124">Yes</span></span>|  
|<span data-ttu-id="d17c3-125">Transporte</span><span class="sxs-lookup"><span data-stu-id="d17c3-125">Transport</span></span>|<span data-ttu-id="d17c3-126">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="d17c3-126">NET.TCP</span></span>|  
|<span data-ttu-id="d17c3-127">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d17c3-127">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="d17c3-128">Servicio</span><span class="sxs-lookup"><span data-stu-id="d17c3-128">Service</span></span>  

 <span data-ttu-id="d17c3-129">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="d17c3-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="d17c3-130">Lleve a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d17c3-130">Do one of the following:</span></span>  
  
- <span data-ttu-id="d17c3-131">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="d17c3-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="d17c3-132">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d17c3-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d17c3-133">Código</span><span class="sxs-lookup"><span data-stu-id="d17c3-133">Code</span></span>  

 <span data-ttu-id="d17c3-134">El código siguiente muestra cómo crear un extremo de servicio que utilice la seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="d17c3-134">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="d17c3-135">Configuración</span><span class="sxs-lookup"><span data-stu-id="d17c3-135">Configuration</span></span>  

 <span data-ttu-id="d17c3-136">Se puede usar la configuración siguiente en lugar del código para configurar el punto de conexión de servicio:</span><span class="sxs-lookup"><span data-stu-id="d17c3-136">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="d17c3-137">Cliente</span><span class="sxs-lookup"><span data-stu-id="d17c3-137">Client</span></span>  

 <span data-ttu-id="d17c3-138">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="d17c3-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="d17c3-139">Lleve a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d17c3-139">Do one of the following:</span></span>  
  
- <span data-ttu-id="d17c3-140">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="d17c3-140">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="d17c3-141">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d17c3-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="d17c3-142">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="d17c3-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="d17c3-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d17c3-143">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="d17c3-144">Código</span><span class="sxs-lookup"><span data-stu-id="d17c3-144">Code</span></span>  

 <span data-ttu-id="d17c3-145">El siguiente código crea el cliente.</span><span class="sxs-lookup"><span data-stu-id="d17c3-145">The following code creates the client.</span></span> <span data-ttu-id="d17c3-146">El enlace se configura para utilizar la seguridad del modo de transporte, con el transporte TCP, con el tipo de credencial de cliente establecido en Windows.</span><span class="sxs-lookup"><span data-stu-id="d17c3-146">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="d17c3-147">Configuración</span><span class="sxs-lookup"><span data-stu-id="d17c3-147">Configuration</span></span>  

 <span data-ttu-id="d17c3-148">La configuración siguiente se puede utilizar en lugar del código para crear el cliente.</span><span class="sxs-lookup"><span data-stu-id="d17c3-148">The following configuration can be used instead of the code to create the client.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d17c3-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="d17c3-149">See also</span></span>

- [<span data-ttu-id="d17c3-150">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="d17c3-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="d17c3-151">Procedimiento para proteger un servicio con credenciales de Windows</span><span class="sxs-lookup"><span data-stu-id="d17c3-151">How to: Secure a Service with Windows Credentials</span></span>](../how-to-secure-a-service-with-windows-credentials.md)
- <span data-ttu-id="d17c3-152">[Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d17c3-152">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
