---
title: Seguridad de transporte con un cliente anónimo
description: Revise este escenario de WCF, que usa la seguridad de transporte para autenticar un servidor mediante el uso de un certificado en el que el cliente confía. El cliente no está autenticado.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: 08cfb8c1a5581f17a251224430018764bed80b0f
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245016"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="e0747-104">Seguridad de transporte con un cliente anónimo</span><span class="sxs-lookup"><span data-stu-id="e0747-104">Transport security with an anonymous client</span></span>

<span data-ttu-id="e0747-105">En este escenario de Windows Communication Foundation (WCF) se usa la seguridad de transporte (HTTPS) para garantizar la confidencialidad y la integridad.</span><span class="sxs-lookup"><span data-stu-id="e0747-105">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="e0747-106">El servidor debe autenticarse con un certificado de Capa de sockets seguros (SSL) y los clientes deben confiar en el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="e0747-106">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="e0747-107">Ningún mecanismo autentica el cliente y es, por lo tanto, anónimo.</span><span class="sxs-lookup"><span data-stu-id="e0747-107">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>

<span data-ttu-id="e0747-108">Para obtener una aplicación de ejemplo, vea [seguridad de transporte de WS](../samples/ws-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="e0747-108">For a sample application, see [WS Transport Security](../samples/ws-transport-security.md).</span></span> <span data-ttu-id="e0747-109">Para obtener más información sobre la seguridad de transporte, vea [información general](transport-security-overview.md)sobre la seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="e0747-109">For more information about transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>

<span data-ttu-id="e0747-110">Para obtener más información sobre el uso de un certificado con un servicio, consulte [trabajar con certificados](working-with-certificates.md) y [Cómo: configurar un puerto con un certificado SSL](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="e0747-110">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

![Utilización de la seguridad de transporte con un cliente anónimo](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|<span data-ttu-id="e0747-112">Característica</span><span class="sxs-lookup"><span data-stu-id="e0747-112">Characteristic</span></span>|<span data-ttu-id="e0747-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0747-113">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="e0747-114">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="e0747-114">Security Mode</span></span>|<span data-ttu-id="e0747-115">Transporte</span><span class="sxs-lookup"><span data-stu-id="e0747-115">Transport</span></span>|
|<span data-ttu-id="e0747-116">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="e0747-116">Interoperability</span></span>|<span data-ttu-id="e0747-117">Con servicios y clientes Web existentes</span><span class="sxs-lookup"><span data-stu-id="e0747-117">With existing Web services and clients</span></span>|
|<span data-ttu-id="e0747-118">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="e0747-118">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="e0747-119">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="e0747-119">Authentication (Client)</span></span>|<span data-ttu-id="e0747-120">Yes</span><span class="sxs-lookup"><span data-stu-id="e0747-120">Yes</span></span><br /><br /> <span data-ttu-id="e0747-121">Nivel de aplicación (sin compatibilidad con WCF)</span><span class="sxs-lookup"><span data-stu-id="e0747-121">Application level (no WCF support)</span></span>|
|<span data-ttu-id="e0747-122">Integridad</span><span class="sxs-lookup"><span data-stu-id="e0747-122">Integrity</span></span>|<span data-ttu-id="e0747-123">Yes</span><span class="sxs-lookup"><span data-stu-id="e0747-123">Yes</span></span>|
|<span data-ttu-id="e0747-124">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="e0747-124">Confidentiality</span></span>|<span data-ttu-id="e0747-125">Yes</span><span class="sxs-lookup"><span data-stu-id="e0747-125">Yes</span></span>|
|<span data-ttu-id="e0747-126">Transporte</span><span class="sxs-lookup"><span data-stu-id="e0747-126">Transport</span></span>|<span data-ttu-id="e0747-127">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e0747-127">HTTPS</span></span>|
|<span data-ttu-id="e0747-128">Enlace</span><span class="sxs-lookup"><span data-stu-id="e0747-128">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="e0747-129">Servicio</span><span class="sxs-lookup"><span data-stu-id="e0747-129">Service</span></span>

<span data-ttu-id="e0747-130">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="e0747-130">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="e0747-131">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="e0747-131">Do one of the following:</span></span>

- <span data-ttu-id="e0747-132">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="e0747-132">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="e0747-133">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e0747-133">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="e0747-134">Código</span><span class="sxs-lookup"><span data-stu-id="e0747-134">Code</span></span>

<span data-ttu-id="e0747-135">El código siguiente muestra cómo crear un extremo mediante la seguridad del transporte:</span><span class="sxs-lookup"><span data-stu-id="e0747-135">The following code shows how to create an endpoint using transport security:</span></span>

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a><span data-ttu-id="e0747-136">Configuración</span><span class="sxs-lookup"><span data-stu-id="e0747-136">Configuration</span></span>

<span data-ttu-id="e0747-137">El código siguiente configura el mismo extremo mediante la configuración.</span><span class="sxs-lookup"><span data-stu-id="e0747-137">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="e0747-138">Ningún mecanismo autentica el cliente y es, por lo tanto, anónimo.</span><span class="sxs-lookup"><span data-stu-id="e0747-138">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="ServiceModel.Calculator">
        <endpoint address="https://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="WSHttpBinding_ICalculator"
                  name="SecuredByTransportEndpoint"
                  contract="ServiceModel.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator">
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a><span data-ttu-id="e0747-139">Cliente</span><span class="sxs-lookup"><span data-stu-id="e0747-139">Client</span></span>

<span data-ttu-id="e0747-140">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="e0747-140">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="e0747-141">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="e0747-141">Do one of the following:</span></span>

- <span data-ttu-id="e0747-142">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="e0747-142">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="e0747-143">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e0747-143">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="e0747-144">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="e0747-144">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="e0747-145">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e0747-145">For example:</span></span>

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="e0747-146">Código</span><span class="sxs-lookup"><span data-stu-id="e0747-146">Code</span></span>

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a><span data-ttu-id="e0747-147">Configuración</span><span class="sxs-lookup"><span data-stu-id="e0747-147">Configuration</span></span>

<span data-ttu-id="e0747-148">Se puede usar la configuración siguiente en lugar del código para configurar el servicio.</span><span class="sxs-lookup"><span data-stu-id="e0747-148">The following configuration can be used instead of the code to set up the service.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="https://machineName/Calculator"
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"
                name="WSHttpBinding_ICalculator" />
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="e0747-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0747-149">See also</span></span>

- [<span data-ttu-id="e0747-150">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="e0747-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="e0747-151">Seguridad de transporte WS</span><span class="sxs-lookup"><span data-stu-id="e0747-151">WS Transport Security</span></span>](../samples/ws-transport-security.md)
- [<span data-ttu-id="e0747-152">Información general de la seguridad del transporte</span><span class="sxs-lookup"><span data-stu-id="e0747-152">Transport Security Overview</span></span>](transport-security-overview.md)
- <span data-ttu-id="e0747-153">[Modelo de seguridad para Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e0747-153">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
