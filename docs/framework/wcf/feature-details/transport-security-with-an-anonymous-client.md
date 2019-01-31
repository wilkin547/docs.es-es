---
title: Seguridad de transporte con clientes anónimos - WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: 20d7e59ba2b4b9dedc0b0daff1c1aa9c5210e61b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260390"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="0caee-102">Seguridad de transporte con clientes anónimos</span><span class="sxs-lookup"><span data-stu-id="0caee-102">Transport security with an anonymous client</span></span>

<span data-ttu-id="0caee-103">Este escenario Windows Communication Foundation (WCF) utiliza la seguridad de transporte (HTTPS) para garantizar la confidencialidad e integridad.</span><span class="sxs-lookup"><span data-stu-id="0caee-103">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="0caee-104">El servidor debe autenticarse con un certificado de Capa de sockets seguros (SSL) y los clientes deben confiar en el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="0caee-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="0caee-105">Ningún mecanismo autentica el cliente y es, por lo tanto, anónimo.</span><span class="sxs-lookup"><span data-stu-id="0caee-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>

<span data-ttu-id="0caee-106">Para una aplicación de ejemplo, vea [seguridad de transporte WS](../samples/ws-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="0caee-106">For a sample application, see [WS Transport Security](../samples/ws-transport-security.md).</span></span> <span data-ttu-id="0caee-107">Para obtener más información acerca de la seguridad de transporte, vea [información general sobre la seguridad de transporte](transport-security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0caee-107">For more information about transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>

<span data-ttu-id="0caee-108">Para obtener más información sobre el uso de un certificado con un servicio, consulte [trabajar con certificados](working-with-certificates.md) y [Cómo: Configurar un puerto con un certificado SSL](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="0caee-108">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

![Utilización de la seguridad de transporte con un cliente anónimo](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|<span data-ttu-id="0caee-110">Característica</span><span class="sxs-lookup"><span data-stu-id="0caee-110">Characteristic</span></span>|<span data-ttu-id="0caee-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="0caee-111">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="0caee-112">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="0caee-112">Security Mode</span></span>|<span data-ttu-id="0caee-113">Transporte</span><span class="sxs-lookup"><span data-stu-id="0caee-113">Transport</span></span>|
|<span data-ttu-id="0caee-114">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="0caee-114">Interoperability</span></span>|<span data-ttu-id="0caee-115">Con servicios y clientes Web existentes</span><span class="sxs-lookup"><span data-stu-id="0caee-115">With existing Web services and clients</span></span>|
|<span data-ttu-id="0caee-116">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="0caee-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="0caee-117">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="0caee-117">Authentication (Client)</span></span>|<span data-ttu-id="0caee-118">Sí</span><span class="sxs-lookup"><span data-stu-id="0caee-118">Yes</span></span><br /><br /> <span data-ttu-id="0caee-119">Nivel de aplicación (no hay compatibilidad WCF)</span><span class="sxs-lookup"><span data-stu-id="0caee-119">Application level (no WCF support)</span></span>|
|<span data-ttu-id="0caee-120">Integridad</span><span class="sxs-lookup"><span data-stu-id="0caee-120">Integrity</span></span>|<span data-ttu-id="0caee-121">Sí</span><span class="sxs-lookup"><span data-stu-id="0caee-121">Yes</span></span>|
|<span data-ttu-id="0caee-122">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="0caee-122">Confidentiality</span></span>|<span data-ttu-id="0caee-123">Sí</span><span class="sxs-lookup"><span data-stu-id="0caee-123">Yes</span></span>|
|<span data-ttu-id="0caee-124">Transporte</span><span class="sxs-lookup"><span data-stu-id="0caee-124">Transport</span></span>|<span data-ttu-id="0caee-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="0caee-125">HTTPS</span></span>|
|<span data-ttu-id="0caee-126">Enlaces</span><span class="sxs-lookup"><span data-stu-id="0caee-126">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="0caee-127">Servicio</span><span class="sxs-lookup"><span data-stu-id="0caee-127">Service</span></span>

<span data-ttu-id="0caee-128">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="0caee-128">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="0caee-129">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0caee-129">Do one of the following:</span></span>

- <span data-ttu-id="0caee-130">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="0caee-130">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="0caee-131">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún extremo.</span><span class="sxs-lookup"><span data-stu-id="0caee-131">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="0caee-132">Código</span><span class="sxs-lookup"><span data-stu-id="0caee-132">Code</span></span>

<span data-ttu-id="0caee-133">El código siguiente muestra cómo crear un punto de conexión mediante la seguridad del transporte:</span><span class="sxs-lookup"><span data-stu-id="0caee-133">The following code shows how to create an endpoint using transport security:</span></span>

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a><span data-ttu-id="0caee-134">Configuración</span><span class="sxs-lookup"><span data-stu-id="0caee-134">Configuration</span></span>

<span data-ttu-id="0caee-135">El código siguiente configura el mismo punto de conexión mediante la configuración.</span><span class="sxs-lookup"><span data-stu-id="0caee-135">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="0caee-136">Ningún mecanismo autentica el cliente y es, por lo tanto, anónimo.</span><span class="sxs-lookup"><span data-stu-id="0caee-136">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>

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

## <a name="client"></a><span data-ttu-id="0caee-137">Cliente</span><span class="sxs-lookup"><span data-stu-id="0caee-137">Client</span></span>

<span data-ttu-id="0caee-138">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="0caee-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="0caee-139">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0caee-139">Do one of the following:</span></span>

- <span data-ttu-id="0caee-140">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="0caee-140">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="0caee-141">Cree un cliente que no defina direcciones de extremo.</span><span class="sxs-lookup"><span data-stu-id="0caee-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="0caee-142">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="0caee-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="0caee-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0caee-143">For example:</span></span>

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="0caee-144">Código</span><span class="sxs-lookup"><span data-stu-id="0caee-144">Code</span></span>

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a><span data-ttu-id="0caee-145">Configuración</span><span class="sxs-lookup"><span data-stu-id="0caee-145">Configuration</span></span>

<span data-ttu-id="0caee-146">Se puede usar la configuración siguiente en lugar del código para configurar el servicio.</span><span class="sxs-lookup"><span data-stu-id="0caee-146">The following configuration can be used instead of the code to set up the service.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0caee-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="0caee-147">See also</span></span>

- [<span data-ttu-id="0caee-148">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="0caee-148">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="0caee-149">Seguridad de transporte WS</span><span class="sxs-lookup"><span data-stu-id="0caee-149">WS Transport Security</span></span>](../samples/ws-transport-security.md)
- [<span data-ttu-id="0caee-150">Información general de la seguridad del transporte</span><span class="sxs-lookup"><span data-stu-id="0caee-150">Transport Security Overview</span></span>](transport-security-overview.md)
- <span data-ttu-id="0caee-151">[Modelo de seguridad de Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="0caee-151">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>