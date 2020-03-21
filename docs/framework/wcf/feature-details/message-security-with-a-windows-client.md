---
title: Seguridad del mensaje con un cliente de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 01e7d0b8-10f9-45c3-a4c5-53d44dc61eb8
ms.openlocfilehash: bcfeb5f863b1dd6cf9171a7fc53c8984ea68ecb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184631"
---
# <a name="message-security-with-a-windows-client"></a><span data-ttu-id="fcc14-102">Seguridad del mensaje con un cliente de Windows</span><span class="sxs-lookup"><span data-stu-id="fcc14-102">Message Security with a Windows Client</span></span>
<span data-ttu-id="fcc14-103">Este escenario muestra un cliente de Windows Communication Foundation (WCF) y un servidor protegido por el modo de seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fcc14-103">This scenario shows a Windows Communication Foundation (WCF) client and server secured by message security mode.</span></span> <span data-ttu-id="fcc14-104">El cliente y el servicio se autentican utilizando las credenciales de Windows.</span><span class="sxs-lookup"><span data-stu-id="fcc14-104">The client and service are authenticated using Windows credentials.</span></span>  
  
 <span data-ttu-id="fcc14-105">![Seguridad de mensajes con un cliente de Windows](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span><span class="sxs-lookup"><span data-stu-id="fcc14-105">![Message security with a Windows client](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span></span>  
  
|<span data-ttu-id="fcc14-106">Característica</span><span class="sxs-lookup"><span data-stu-id="fcc14-106">Characteristic</span></span>|<span data-ttu-id="fcc14-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fcc14-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="fcc14-108">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="fcc14-108">Security Mode</span></span>|<span data-ttu-id="fcc14-109">Message</span><span class="sxs-lookup"><span data-stu-id="fcc14-109">Message</span></span>|  
|<span data-ttu-id="fcc14-110">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="fcc14-110">Interoperability</span></span>|<span data-ttu-id="fcc14-111">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="fcc14-111">WCF Only</span></span>|  
|<span data-ttu-id="fcc14-112">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="fcc14-112">Authentication (Server)</span></span>|<span data-ttu-id="fcc14-113">Autenticación mutua del servidor y el cliente</span><span class="sxs-lookup"><span data-stu-id="fcc14-113">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="fcc14-114">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="fcc14-114">Authentication (Client)</span></span>|<span data-ttu-id="fcc14-115">Autenticación mutua del servidor y el cliente</span><span class="sxs-lookup"><span data-stu-id="fcc14-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="fcc14-116">Integridad</span><span class="sxs-lookup"><span data-stu-id="fcc14-116">Integrity</span></span>|<span data-ttu-id="fcc14-117">Sí, mediante el contexto de seguridad compartido</span><span class="sxs-lookup"><span data-stu-id="fcc14-117">Yes, using shared security context</span></span>|  
|<span data-ttu-id="fcc14-118">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="fcc14-118">Confidentiality</span></span>|<span data-ttu-id="fcc14-119">Sí, mediante el contexto de seguridad compartido</span><span class="sxs-lookup"><span data-stu-id="fcc14-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="fcc14-120">Transporte</span><span class="sxs-lookup"><span data-stu-id="fcc14-120">Transport</span></span>|<span data-ttu-id="fcc14-121">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="fcc14-121">NET.TCP</span></span>|  
|<span data-ttu-id="fcc14-122">Enlace</span><span class="sxs-lookup"><span data-stu-id="fcc14-122">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="fcc14-123">Servicio</span><span class="sxs-lookup"><span data-stu-id="fcc14-123">Service</span></span>  
 <span data-ttu-id="fcc14-124">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="fcc14-124">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="fcc14-125">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="fcc14-125">Do one of the following:</span></span>  
  
- <span data-ttu-id="fcc14-126">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="fcc14-126">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="fcc14-127">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="fcc14-127">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="fcc14-128">Código</span><span class="sxs-lookup"><span data-stu-id="fcc14-128">Code</span></span>  
 <span data-ttu-id="fcc14-129">El código siguiente muestra cómo crear un extremo de servicio que utiliza la seguridad del mensaje para establecer un contexto seguro con una máquina Windows.</span><span class="sxs-lookup"><span data-stu-id="fcc14-129">The following code shows how to create a service endpoint that uses message security to establish a secure context with a Windows machine.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#11)]
 [!code-vb[C_SecurityScenarios#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#11)]  
  
### <a name="configuration"></a><span data-ttu-id="fcc14-130">Configuración</span><span class="sxs-lookup"><span data-stu-id="fcc14-130">Configuration</span></span>  
 <span data-ttu-id="fcc14-131">Se puede usar la configuración siguiente en lugar del código para preparar el servicio:</span><span class="sxs-lookup"><span data-stu-id="fcc14-131">The following configuration can be used instead of the code to set up the service:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration=""  
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"  
                  binding="netTcpBinding"  
                  bindingConfiguration="Windows"  
                  name="WindowsOverMessage"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="Windows">  
          <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="fcc14-132">Remoto</span><span class="sxs-lookup"><span data-stu-id="fcc14-132">Client</span></span>  
 <span data-ttu-id="fcc14-133">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="fcc14-133">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="fcc14-134">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="fcc14-134">Do one of the following:</span></span>  
  
- <span data-ttu-id="fcc14-135">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="fcc14-135">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="fcc14-136">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="fcc14-136">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="fcc14-137">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="fcc14-137">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="fcc14-138">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fcc14-138">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="fcc14-139">Código</span><span class="sxs-lookup"><span data-stu-id="fcc14-139">Code</span></span>  
 <span data-ttu-id="fcc14-140">El siguiente código crea un cliente.</span><span class="sxs-lookup"><span data-stu-id="fcc14-140">The following code creates a client.</span></span> <span data-ttu-id="fcc14-141">El enlace es para la seguridad del modo de mensaje y el tipo de credencial de cliente está establecido para `Windows`.</span><span class="sxs-lookup"><span data-stu-id="fcc14-141">The binding is to Message mode security, and the client credential type is set to `Windows`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#18)]
 [!code-vb[C_SecurityScenarios#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#18)]  
  
### <a name="configuration"></a><span data-ttu-id="fcc14-142">Configuración</span><span class="sxs-lookup"><span data-stu-id="fcc14-142">Configuration</span></span>  
 <span data-ttu-id="fcc14-143">La configuración siguiente se utiliza para establecer las propiedades del cliente.</span><span class="sxs-lookup"><span data-stu-id="fcc14-143">The following configuration is used to set the client properties.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
         <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator"
                binding="netTcpBinding"  
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fcc14-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fcc14-144">See also</span></span>

- [<span data-ttu-id="fcc14-145">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="fcc14-145">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="fcc14-146">[Modelo de seguridad para Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="fcc14-146">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
