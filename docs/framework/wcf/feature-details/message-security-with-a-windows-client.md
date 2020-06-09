---
title: Seguridad del mensaje con un cliente de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 01e7d0b8-10f9-45c3-a4c5-53d44dc61eb8
ms.openlocfilehash: dcb311523c6ec41b62f6e69fe6bc7635b9d49708
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595237"
---
# <a name="message-security-with-a-windows-client"></a><span data-ttu-id="1241c-102">Seguridad del mensaje con un cliente de Windows</span><span class="sxs-lookup"><span data-stu-id="1241c-102">Message Security with a Windows Client</span></span>
<span data-ttu-id="1241c-103">Este escenario muestra un cliente y un servidor Windows Communication Foundation (WCF) protegidos por el modo de seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1241c-103">This scenario shows a Windows Communication Foundation (WCF) client and server secured by message security mode.</span></span> <span data-ttu-id="1241c-104">El cliente y el servicio se autentican utilizando las credenciales de Windows.</span><span class="sxs-lookup"><span data-stu-id="1241c-104">The client and service are authenticated using Windows credentials.</span></span>  
  
 <span data-ttu-id="1241c-105">![Seguridad de mensajes con un cliente de Windows](media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span><span class="sxs-lookup"><span data-stu-id="1241c-105">![Message security with a Windows client](media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span></span>  
  
|<span data-ttu-id="1241c-106">Característica</span><span class="sxs-lookup"><span data-stu-id="1241c-106">Characteristic</span></span>|<span data-ttu-id="1241c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1241c-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="1241c-108">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="1241c-108">Security Mode</span></span>|<span data-ttu-id="1241c-109">Message</span><span class="sxs-lookup"><span data-stu-id="1241c-109">Message</span></span>|  
|<span data-ttu-id="1241c-110">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="1241c-110">Interoperability</span></span>|<span data-ttu-id="1241c-111">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="1241c-111">WCF Only</span></span>|  
|<span data-ttu-id="1241c-112">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="1241c-112">Authentication (Server)</span></span>|<span data-ttu-id="1241c-113">Autenticación mutua del servidor y el cliente</span><span class="sxs-lookup"><span data-stu-id="1241c-113">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="1241c-114">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="1241c-114">Authentication (Client)</span></span>|<span data-ttu-id="1241c-115">Autenticación mutua del servidor y el cliente</span><span class="sxs-lookup"><span data-stu-id="1241c-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="1241c-116">Integridad</span><span class="sxs-lookup"><span data-stu-id="1241c-116">Integrity</span></span>|<span data-ttu-id="1241c-117">Sí, mediante el contexto de seguridad compartido</span><span class="sxs-lookup"><span data-stu-id="1241c-117">Yes, using shared security context</span></span>|  
|<span data-ttu-id="1241c-118">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="1241c-118">Confidentiality</span></span>|<span data-ttu-id="1241c-119">Sí, mediante el contexto de seguridad compartido</span><span class="sxs-lookup"><span data-stu-id="1241c-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="1241c-120">Transporte</span><span class="sxs-lookup"><span data-stu-id="1241c-120">Transport</span></span>|<span data-ttu-id="1241c-121">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="1241c-121">NET.TCP</span></span>|  
|<span data-ttu-id="1241c-122">Enlace</span><span class="sxs-lookup"><span data-stu-id="1241c-122">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="1241c-123">web de Office</span><span class="sxs-lookup"><span data-stu-id="1241c-123">Service</span></span>  
 <span data-ttu-id="1241c-124">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="1241c-124">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="1241c-125">Lleve a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="1241c-125">Do one of the following:</span></span>  
  
- <span data-ttu-id="1241c-126">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="1241c-126">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="1241c-127">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1241c-127">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1241c-128">Código</span><span class="sxs-lookup"><span data-stu-id="1241c-128">Code</span></span>  
 <span data-ttu-id="1241c-129">El código siguiente muestra cómo crear un extremo de servicio que utiliza la seguridad del mensaje para establecer un contexto seguro con una máquina Windows.</span><span class="sxs-lookup"><span data-stu-id="1241c-129">The following code shows how to create a service endpoint that uses message security to establish a secure context with a Windows machine.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#11)]
 [!code-vb[C_SecurityScenarios#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#11)]  
  
### <a name="configuration"></a><span data-ttu-id="1241c-130">Configuración</span><span class="sxs-lookup"><span data-stu-id="1241c-130">Configuration</span></span>  
 <span data-ttu-id="1241c-131">Se puede usar la configuración siguiente en lugar del código para preparar el servicio:</span><span class="sxs-lookup"><span data-stu-id="1241c-131">The following configuration can be used instead of the code to set up the service:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="1241c-132">Cliente</span><span class="sxs-lookup"><span data-stu-id="1241c-132">Client</span></span>  
 <span data-ttu-id="1241c-133">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="1241c-133">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="1241c-134">Lleve a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="1241c-134">Do one of the following:</span></span>  
  
- <span data-ttu-id="1241c-135">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="1241c-135">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="1241c-136">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1241c-136">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="1241c-137">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="1241c-137">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="1241c-138">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1241c-138">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="1241c-139">Código</span><span class="sxs-lookup"><span data-stu-id="1241c-139">Code</span></span>  
 <span data-ttu-id="1241c-140">El siguiente código crea un cliente.</span><span class="sxs-lookup"><span data-stu-id="1241c-140">The following code creates a client.</span></span> <span data-ttu-id="1241c-141">El enlace es para la seguridad del modo de mensaje y el tipo de credencial de cliente está establecido para `Windows`.</span><span class="sxs-lookup"><span data-stu-id="1241c-141">The binding is to Message mode security, and the client credential type is set to `Windows`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#18)]
 [!code-vb[C_SecurityScenarios#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#18)]  
  
### <a name="configuration"></a><span data-ttu-id="1241c-142">Configuración</span><span class="sxs-lookup"><span data-stu-id="1241c-142">Configuration</span></span>  
 <span data-ttu-id="1241c-143">La configuración siguiente se utiliza para establecer las propiedades del cliente.</span><span class="sxs-lookup"><span data-stu-id="1241c-143">The following configuration is used to set the client properties.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1241c-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="1241c-144">See also</span></span>

- [<span data-ttu-id="1241c-145">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="1241c-145">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="1241c-146">[Modelo de seguridad para Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="1241c-146">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
