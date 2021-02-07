---
description: 'Más información acerca de: seguridad de mensajes con un cliente anónimo'
title: Seguridad de mensajes con clientes anónimos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cad53e1a-b7c9-4064-bc87-508c3d1dce49
ms.openlocfilehash: 921ddd9e8e7d2a860f3516c452870bc2bb150911
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726980"
---
# <a name="message-security-with-an-anonymous-client"></a><span data-ttu-id="2f26a-103">Seguridad de mensajes con clientes anónimos</span><span class="sxs-lookup"><span data-stu-id="2f26a-103">Message Security with an Anonymous Client</span></span>

<span data-ttu-id="2f26a-104">En el siguiente escenario se muestra un cliente y un servicio protegidos por la seguridad de mensajes de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2f26a-104">The following scenario shows a client and service secured by Windows Communication Foundation (WCF) message security.</span></span> <span data-ttu-id="2f26a-105">Un objetivo del diseño es usar la seguridad del mensaje en lugar de la seguridad de transporte, para que en el futuro pueda admitir un modelo basado en notificaciones más completo.</span><span class="sxs-lookup"><span data-stu-id="2f26a-105">A design goal is to use message security rather than transport security, so that in the future it can support a richer claims-based model.</span></span> <span data-ttu-id="2f26a-106">Para obtener más información sobre el uso de notificaciones enriquecidas para la autorización, consulte [Administración de notificaciones y autorización con el modelo de identidad](managing-claims-and-authorization-with-the-identity-model.md).</span><span class="sxs-lookup"><span data-stu-id="2f26a-106">For more information about using rich claims for authorization, see [Managing Claims and Authorization with the Identity Model](managing-claims-and-authorization-with-the-identity-model.md).</span></span>

<span data-ttu-id="2f26a-107">Para obtener una aplicación de ejemplo, vea [seguridad de mensajes anónima](../samples/message-security-anonymous.md).</span><span class="sxs-lookup"><span data-stu-id="2f26a-107">For a sample application, see [Message Security Anonymous](../samples/message-security-anonymous.md).</span></span>

<span data-ttu-id="2f26a-108">![Seguridad de mensajes con un cliente anónimo](media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span><span class="sxs-lookup"><span data-stu-id="2f26a-108">![Message security with an anonymous client](media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span></span>

|<span data-ttu-id="2f26a-109">Característica</span><span class="sxs-lookup"><span data-stu-id="2f26a-109">Characteristic</span></span>|<span data-ttu-id="2f26a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f26a-110">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="2f26a-111">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="2f26a-111">Security Mode</span></span>|<span data-ttu-id="2f26a-112">Message</span><span class="sxs-lookup"><span data-stu-id="2f26a-112">Message</span></span>|
|<span data-ttu-id="2f26a-113">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="2f26a-113">Interoperability</span></span>|<span data-ttu-id="2f26a-114">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="2f26a-114">WCF only</span></span>|
|<span data-ttu-id="2f26a-115">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="2f26a-115">Authentication (Server)</span></span>|<span data-ttu-id="2f26a-116">La negociación inicial requiere la autenticación del servidor, pero no la autenticación del cliente</span><span class="sxs-lookup"><span data-stu-id="2f26a-116">Initial negotiation requires server authentication, but not client authentication</span></span>|
|<span data-ttu-id="2f26a-117">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="2f26a-117">Authentication (Client)</span></span>|<span data-ttu-id="2f26a-118">None</span><span class="sxs-lookup"><span data-stu-id="2f26a-118">None</span></span>|
|<span data-ttu-id="2f26a-119">Integridad</span><span class="sxs-lookup"><span data-stu-id="2f26a-119">Integrity</span></span>|<span data-ttu-id="2f26a-120">Sí, mediante el contexto de seguridad compartido</span><span class="sxs-lookup"><span data-stu-id="2f26a-120">Yes, using shared security context</span></span>|
|<span data-ttu-id="2f26a-121">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="2f26a-121">Confidentiality</span></span>|<span data-ttu-id="2f26a-122">Sí, mediante el contexto de seguridad compartido</span><span class="sxs-lookup"><span data-stu-id="2f26a-122">Yes, using shared security context</span></span>|
|<span data-ttu-id="2f26a-123">Transporte</span><span class="sxs-lookup"><span data-stu-id="2f26a-123">Transport</span></span>|<span data-ttu-id="2f26a-124">HTTP</span><span class="sxs-lookup"><span data-stu-id="2f26a-124">HTTP</span></span>|

## <a name="service"></a><span data-ttu-id="2f26a-125">Servicio</span><span class="sxs-lookup"><span data-stu-id="2f26a-125">Service</span></span>

<span data-ttu-id="2f26a-126">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="2f26a-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="2f26a-127">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2f26a-127">Do one of the following:</span></span>

- <span data-ttu-id="2f26a-128">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="2f26a-128">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="2f26a-129">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2f26a-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="2f26a-130">Código</span><span class="sxs-lookup"><span data-stu-id="2f26a-130">Code</span></span>

<span data-ttu-id="2f26a-131">El código siguiente muestra cómo crear un extremo de servicio que utiliza la seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2f26a-131">The following code shows how to create a service endpoint that uses message security.</span></span>

[!code-csharp[C_SecurityScenarios#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#8)]
[!code-vb[C_SecurityScenarios#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#8)]

### <a name="configuration"></a><span data-ttu-id="2f26a-132">Configuración</span><span class="sxs-lookup"><span data-stu-id="2f26a-132">Configuration</span></span>

<span data-ttu-id="2f26a-133">En lugar del código, se puede utilizar la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="2f26a-133">The following configuration can be used instead of the code.</span></span> <span data-ttu-id="2f26a-134">El elemento de comportamiento del servicio se utiliza para especificar un certificado utilizado para autenticar el servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="2f26a-134">The service behavior element is used to specify a certificate that is used to authenticate the service to the client.</span></span> <span data-ttu-id="2f26a-135">El elemento de servicio debe especificar el comportamiento mediante el atributo `behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="2f26a-135">The service element must specify the behavior using the `behaviorConfiguration` attribute.</span></span> <span data-ttu-id="2f26a-136">El elemento de enlace especifica que el tipo de credencial de cliente es `None`, de modo que permite a los clientes anónimos utilizar el servicio.</span><span class="sxs-lookup"><span data-stu-id="2f26a-136">The binding element specifies that the client credential type is `None`, allowing anonymous clients to use the service.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior name="ServiceCredentialsBehavior">
          <serviceCredentials>
            <serviceCertificate findValue="contoso.com"
                                storeLocation="LocalMachine"
                                storeName="My" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <services>
      <service behaviorConfiguration="ServiceCredentialsBehavior"
               name="ServiceModel.Calculator">
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="WSHttpBinding_ICalculator"
                  name="CalculatorService"
                  contract="ServiceModel.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Message">
            <message clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a><span data-ttu-id="2f26a-137">Cliente</span><span class="sxs-lookup"><span data-stu-id="2f26a-137">Client</span></span>

<span data-ttu-id="2f26a-138">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="2f26a-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="2f26a-139">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2f26a-139">Do one of the following:</span></span>

- <span data-ttu-id="2f26a-140">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="2f26a-140">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="2f26a-141">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2f26a-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="2f26a-142">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="2f26a-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="2f26a-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2f26a-143">For example:</span></span>

    [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
    [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="2f26a-144">Código</span><span class="sxs-lookup"><span data-stu-id="2f26a-144">Code</span></span>

<span data-ttu-id="2f26a-145">En el ejemplo de código siguiente se crea una instancia de cliente.</span><span class="sxs-lookup"><span data-stu-id="2f26a-145">The following code creates an instance of the client.</span></span> <span data-ttu-id="2f26a-146">El enlace utiliza seguridad en modo de mensaje y el tipo de credencial de cliente está establecido como ninguno.</span><span class="sxs-lookup"><span data-stu-id="2f26a-146">The binding uses message mode security, and the client credential type is set to none.</span></span>

[!code-csharp[C_SecurityScenarios#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#15)]
[!code-vb[C_SecurityScenarios#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#15)]

### <a name="configuration"></a><span data-ttu-id="2f26a-147">Configuración</span><span class="sxs-lookup"><span data-stu-id="2f26a-147">Configuration</span></span>

<span data-ttu-id="2f26a-148">El siguiente código configura el cliente.</span><span class="sxs-lookup"><span data-stu-id="2f26a-148">The following code configures the client.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Message">
            <message clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="http://machineName/Calculator"
        binding="wsHttpBinding"
        bindingConfiguration="WSHttpBinding_ICalculator"
        contract="ICalculator"
        name="WSHttpBinding_ICalculator">
        <identity>
          <dns value="contoso.com" />
        </identity>
      </endpoint>
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="2f26a-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f26a-149">See also</span></span>

- [<span data-ttu-id="2f26a-150">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="2f26a-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="2f26a-151">Seguridad distribuida de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="2f26a-151">Distributed Application Security</span></span>](distributed-application-security.md)
- [<span data-ttu-id="2f26a-152">Seguridad de mensaje anónima</span><span class="sxs-lookup"><span data-stu-id="2f26a-152">Message Security Anonymous</span></span>](../samples/message-security-anonymous.md)
- [<span data-ttu-id="2f26a-153">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="2f26a-153">Service Identity and Authentication</span></span>](service-identity-and-authentication.md)
- <span data-ttu-id="2f26a-154">[Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="2f26a-154">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
