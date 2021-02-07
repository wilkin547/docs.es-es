---
description: 'Más información acerca de: seguridad de mensajes con un cliente de Windows'
title: Seguridad del mensaje con un cliente de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 01e7d0b8-10f9-45c3-a4c5-53d44dc61eb8
ms.openlocfilehash: 97d415f68b4374ab2b18360347d7753f6be51313
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756102"
---
# <a name="message-security-with-a-windows-client"></a><span data-ttu-id="a6a5d-103">Seguridad del mensaje con un cliente de Windows</span><span class="sxs-lookup"><span data-stu-id="a6a5d-103">Message Security with a Windows Client</span></span>

<span data-ttu-id="a6a5d-104">Este escenario muestra un cliente y un servidor Windows Communication Foundation (WCF) protegidos por el modo de seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a6a5d-104">This scenario shows a Windows Communication Foundation (WCF) client and server secured by message security mode.</span></span> <span data-ttu-id="a6a5d-105">El cliente y el servicio se autentican utilizando las credenciales de Windows.</span><span class="sxs-lookup"><span data-stu-id="a6a5d-105">The client and service are authenticated using Windows credentials.</span></span>  
  
 <span data-ttu-id="a6a5d-106">![Seguridad de mensajes con un cliente de Windows](media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span><span class="sxs-lookup"><span data-stu-id="a6a5d-106">![Message security with a Windows client](media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span></span>  
  
|<span data-ttu-id="a6a5d-107">Característica</span><span class="sxs-lookup"><span data-stu-id="a6a5d-107">Characteristic</span></span>|<span data-ttu-id="a6a5d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6a5d-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a6a5d-109">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="a6a5d-109">Security Mode</span></span>|<span data-ttu-id="a6a5d-110">Message</span><span class="sxs-lookup"><span data-stu-id="a6a5d-110">Message</span></span>|  
|<span data-ttu-id="a6a5d-111">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="a6a5d-111">Interoperability</span></span>|<span data-ttu-id="a6a5d-112">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="a6a5d-112">WCF Only</span></span>|  
|<span data-ttu-id="a6a5d-113">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="a6a5d-113">Authentication (Server)</span></span>|<span data-ttu-id="a6a5d-114">Autenticación mutua del servidor y el cliente</span><span class="sxs-lookup"><span data-stu-id="a6a5d-114">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="a6a5d-115">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="a6a5d-115">Authentication (Client)</span></span>|<span data-ttu-id="a6a5d-116">Autenticación mutua del servidor y el cliente</span><span class="sxs-lookup"><span data-stu-id="a6a5d-116">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="a6a5d-117">Integridad</span><span class="sxs-lookup"><span data-stu-id="a6a5d-117">Integrity</span></span>|<span data-ttu-id="a6a5d-118">Sí, mediante el contexto de seguridad compartido</span><span class="sxs-lookup"><span data-stu-id="a6a5d-118">Yes, using shared security context</span></span>|  
|<span data-ttu-id="a6a5d-119">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="a6a5d-119">Confidentiality</span></span>|<span data-ttu-id="a6a5d-120">Sí, mediante el contexto de seguridad compartido</span><span class="sxs-lookup"><span data-stu-id="a6a5d-120">Yes, using shared security context</span></span>|  
|<span data-ttu-id="a6a5d-121">Transporte</span><span class="sxs-lookup"><span data-stu-id="a6a5d-121">Transport</span></span>|<span data-ttu-id="a6a5d-122">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="a6a5d-122">NET.TCP</span></span>|  
|<span data-ttu-id="a6a5d-123">Enlace</span><span class="sxs-lookup"><span data-stu-id="a6a5d-123">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="a6a5d-124">Servicio</span><span class="sxs-lookup"><span data-stu-id="a6a5d-124">Service</span></span>  

 <span data-ttu-id="a6a5d-125">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="a6a5d-125">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="a6a5d-126">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="a6a5d-126">Do one of the following:</span></span>  
  
- <span data-ttu-id="a6a5d-127">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="a6a5d-127">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="a6a5d-128">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a6a5d-128">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a6a5d-129">Código</span><span class="sxs-lookup"><span data-stu-id="a6a5d-129">Code</span></span>  

 <span data-ttu-id="a6a5d-130">El código siguiente muestra cómo crear un extremo de servicio que utiliza la seguridad del mensaje para establecer un contexto seguro con una máquina Windows.</span><span class="sxs-lookup"><span data-stu-id="a6a5d-130">The following code shows how to create a service endpoint that uses message security to establish a secure context with a Windows machine.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#11)]
 [!code-vb[C_SecurityScenarios#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#11)]  
  
### <a name="configuration"></a><span data-ttu-id="a6a5d-131">Configuración</span><span class="sxs-lookup"><span data-stu-id="a6a5d-131">Configuration</span></span>  

 <span data-ttu-id="a6a5d-132">Se puede usar la configuración siguiente en lugar del código para preparar el servicio:</span><span class="sxs-lookup"><span data-stu-id="a6a5d-132">The following configuration can be used instead of the code to set up the service:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="a6a5d-133">Cliente</span><span class="sxs-lookup"><span data-stu-id="a6a5d-133">Client</span></span>  

 <span data-ttu-id="a6a5d-134">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="a6a5d-134">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="a6a5d-135">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="a6a5d-135">Do one of the following:</span></span>  
  
- <span data-ttu-id="a6a5d-136">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="a6a5d-136">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="a6a5d-137">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a6a5d-137">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="a6a5d-138">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="a6a5d-138">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="a6a5d-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a6a5d-139">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="a6a5d-140">Código</span><span class="sxs-lookup"><span data-stu-id="a6a5d-140">Code</span></span>  

 <span data-ttu-id="a6a5d-141">El siguiente código crea un cliente.</span><span class="sxs-lookup"><span data-stu-id="a6a5d-141">The following code creates a client.</span></span> <span data-ttu-id="a6a5d-142">El enlace es para la seguridad del modo de mensaje y el tipo de credencial de cliente está establecido para `Windows`.</span><span class="sxs-lookup"><span data-stu-id="a6a5d-142">The binding is to Message mode security, and the client credential type is set to `Windows`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#18)]
 [!code-vb[C_SecurityScenarios#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#18)]  
  
### <a name="configuration"></a><span data-ttu-id="a6a5d-143">Configuración</span><span class="sxs-lookup"><span data-stu-id="a6a5d-143">Configuration</span></span>  

 <span data-ttu-id="a6a5d-144">La configuración siguiente se utiliza para establecer las propiedades del cliente.</span><span class="sxs-lookup"><span data-stu-id="a6a5d-144">The following configuration is used to set the client properties.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a6a5d-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6a5d-145">See also</span></span>

- [<span data-ttu-id="a6a5d-146">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="a6a5d-146">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="a6a5d-147">[Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="a6a5d-147">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
