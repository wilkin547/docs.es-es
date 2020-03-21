---
title: Seguridad de mensajes con certificados mutuos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99d7a528-7ae4-4d39-a0f9-3066ea237de0
ms.openlocfilehash: e2aaf1a5e6ae1074a81c08fc798f22ea5e9ce139
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184612"
---
# <a name="message-security-with-mutual-certificates"></a><span data-ttu-id="d7a55-102">Seguridad de mensajes con certificados mutuos</span><span class="sxs-lookup"><span data-stu-id="d7a55-102">Message Security with Mutual Certificates</span></span>
<span data-ttu-id="d7a55-103">En el escenario siguiente se muestra un servicio de Windows Communication Foundation (WCF) y un cliente protegido mediante el modo de seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d7a55-103">The following scenario shows a Windows Communication Foundation (WCF) service and client secured using message security mode.</span></span> <span data-ttu-id="d7a55-104">El cliente y el servicio se autentican con certificados.</span><span class="sxs-lookup"><span data-stu-id="d7a55-104">The client and the service are authenticated with certificates.</span></span>  
  
 <span data-ttu-id="d7a55-105">Este escenario es interoperable porque utiliza WS-Security con el perfil de token de certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="d7a55-105">This scenario is interoperable because it uses WS-Security with the X.509 certificate token profile.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7a55-106">Este escenario no realiza negociación del certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="d7a55-106">This scenario does not perform negotiation of the service certificate.</span></span> <span data-ttu-id="d7a55-107">El certificado del servicio debe ser proporcionado de antemano al cliente de cualquier comunicación.</span><span class="sxs-lookup"><span data-stu-id="d7a55-107">The service certificate must be provided to the client in advance of any communication.</span></span> <span data-ttu-id="d7a55-108">El certificado de servidor se puede distribuir con la aplicación o puede ser proporcionado en una comunicación fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="d7a55-108">The server certificate can be distributed with the application or provided in an out-of-band communication.</span></span>  
  
 <span data-ttu-id="d7a55-109">![Seguridad de mensajes con certificados mutuos](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span><span class="sxs-lookup"><span data-stu-id="d7a55-109">![Message security with mutual certificates](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span></span>  
  
|<span data-ttu-id="d7a55-110">Característica</span><span class="sxs-lookup"><span data-stu-id="d7a55-110">Characteristic</span></span>|<span data-ttu-id="d7a55-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7a55-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d7a55-112">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="d7a55-112">Security Mode</span></span>|<span data-ttu-id="d7a55-113">Message</span><span class="sxs-lookup"><span data-stu-id="d7a55-113">Message</span></span>|  
|<span data-ttu-id="d7a55-114">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="d7a55-114">Interoperability</span></span>|<span data-ttu-id="d7a55-115">Sí, clientes y servicios compatibles con WS-Security y el perfil de token de certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="d7a55-115">Yes, with WS-Security and X.509 certificate token profile compatible clients and services.</span></span>|  
|<span data-ttu-id="d7a55-116">Authentication</span><span class="sxs-lookup"><span data-stu-id="d7a55-116">Authentication</span></span>|<span data-ttu-id="d7a55-117">Autenticación mutua del servidor y el cliente.</span><span class="sxs-lookup"><span data-stu-id="d7a55-117">Mutual authentication of the server and client.</span></span>|  
|<span data-ttu-id="d7a55-118">Integridad</span><span class="sxs-lookup"><span data-stu-id="d7a55-118">Integrity</span></span>|<span data-ttu-id="d7a55-119">Sí</span><span class="sxs-lookup"><span data-stu-id="d7a55-119">Yes</span></span>|  
|<span data-ttu-id="d7a55-120">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="d7a55-120">Confidentiality</span></span>|<span data-ttu-id="d7a55-121">Sí</span><span class="sxs-lookup"><span data-stu-id="d7a55-121">Yes</span></span>|  
|<span data-ttu-id="d7a55-122">Transporte</span><span class="sxs-lookup"><span data-stu-id="d7a55-122">Transport</span></span>|<span data-ttu-id="d7a55-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="d7a55-123">HTTP</span></span>|  
|<span data-ttu-id="d7a55-124">Enlace</span><span class="sxs-lookup"><span data-stu-id="d7a55-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="d7a55-125">Servicio</span><span class="sxs-lookup"><span data-stu-id="d7a55-125">Service</span></span>  
 <span data-ttu-id="d7a55-126">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="d7a55-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="d7a55-127">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d7a55-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="d7a55-128">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="d7a55-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="d7a55-129">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d7a55-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d7a55-130">Código</span><span class="sxs-lookup"><span data-stu-id="d7a55-130">Code</span></span>  
 <span data-ttu-id="d7a55-131">El código siguiente muestra cómo crear un punto de conexión de servicio que utilice la seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d7a55-131">The following code shows creates a service endpoint that uses message security.</span></span> <span data-ttu-id="d7a55-132">El servicio exige a un certificado que se autentique.</span><span class="sxs-lookup"><span data-stu-id="d7a55-132">The service requires a certificate to authenticate itself.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#13)]
 [!code-vb[C_SecurityScenarios#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#13)]  
  
### <a name="configuration"></a><span data-ttu-id="d7a55-133">Configuración</span><span class="sxs-lookup"><span data-stu-id="d7a55-133">Configuration</span></span>  
 <span data-ttu-id="d7a55-134">La configuración siguiente se puede utilizar en lugar del código para crear el mismo servicio.</span><span class="sxs-lookup"><span data-stu-id="d7a55-134">The following configuration can be used instead of the code to create the same service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="serviceCredentialBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"
                                storeLocation="LocalMachine"  
                                storeName="My"
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="serviceCredentialBehavior"
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"  
                  bindingConfiguration="InteropCertificateBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="InteropCertificateBinding">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"  
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="d7a55-135">Remoto</span><span class="sxs-lookup"><span data-stu-id="d7a55-135">Client</span></span>  
 <span data-ttu-id="d7a55-136">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="d7a55-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="d7a55-137">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d7a55-137">Do one of the following:</span></span>  
  
- <span data-ttu-id="d7a55-138">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="d7a55-138">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="d7a55-139">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d7a55-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="d7a55-140">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="d7a55-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="d7a55-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d7a55-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="d7a55-142">Código</span><span class="sxs-lookup"><span data-stu-id="d7a55-142">Code</span></span>  
 <span data-ttu-id="d7a55-143">El siguiente código crea el cliente.</span><span class="sxs-lookup"><span data-stu-id="d7a55-143">The following code creates the client.</span></span> <span data-ttu-id="d7a55-144">El modo de seguridad se establece en mensaje, y el tipo de credencial de cliente se establece en certificado.</span><span class="sxs-lookup"><span data-stu-id="d7a55-144">The security mode is set to Message, and the client credential type is set to Certificate.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#20)]
 [!code-vb[C_SecurityScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#20)]  
  
### <a name="configuration"></a><span data-ttu-id="d7a55-145">Configuración</span><span class="sxs-lookup"><span data-stu-id="d7a55-145">Configuration</span></span>  
 <span data-ttu-id="d7a55-146">Lo siguiente configura el cliente.</span><span class="sxs-lookup"><span data-stu-id="d7a55-146">The following configures the client.</span></span> <span data-ttu-id="d7a55-147">Se debe especificar un certificado de cliente mediante [ \<clientCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="d7a55-147">A client certificate must be specified using the [\<clientCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span> <span data-ttu-id="d7a55-148">Además, el certificado de servicio se especifica mediante [ \<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="d7a55-148">Also, the service certificate is specified using the [\<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"
                 storeLocation="CurrentUser"  
                 storeName="My"  
                 x509FindType="FindBySubjectName" />  
            <serviceCertificate>  
              <defaultCertificate findValue="Contoso.com"
                                  storeLocation="CurrentUser"  
                                  storeName="TrustedPeople"  
                                  x509FindType="FindBySubjectName" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate"
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                behaviorConfiguration="ClientCredentialsBehavior"  
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <certificate encodedValue="Encoded_Value_Not_Shown" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7a55-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7a55-149">See also</span></span>

- [<span data-ttu-id="d7a55-150">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="d7a55-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="d7a55-151">[Modelo de seguridad para Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d7a55-151">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
- <span data-ttu-id="d7a55-152">[Cómo: Crear e instalar certificados temporales en WCF para la seguridad del transporte durante el desarrollo](https://docs.microsoft.com/previous-versions/msp-n-p/ff648498(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="d7a55-152">[How to: Create and Install Temporary Certificates in WCF for Transport Security During Development](https://docs.microsoft.com/previous-versions/msp-n-p/ff648498(v=pandp.10))</span></span>
