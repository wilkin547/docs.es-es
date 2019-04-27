---
title: Seguridad de mensajes con certificados mutuos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99d7a528-7ae4-4d39-a0f9-3066ea237de0
ms.openlocfilehash: 8fc8d6d4a63b7a752fb8c26991d904761fdcebdd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923075"
---
# <a name="message-security-with-mutual-certificates"></a><span data-ttu-id="f8ce8-102">Seguridad de mensajes con certificados mutuos</span><span class="sxs-lookup"><span data-stu-id="f8ce8-102">Message Security with Mutual Certificates</span></span>
<span data-ttu-id="f8ce8-103">El escenario siguiente muestra un servicio de Windows Communication Foundation (WCF) y el cliente protegido utilizando el modo de seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-103">The following scenario shows a Windows Communication Foundation (WCF) service and client secured using message security mode.</span></span> <span data-ttu-id="f8ce8-104">El cliente y el servicio se autentican con certificados.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-104">The client and the service are authenticated with certificates.</span></span>  
  
 <span data-ttu-id="f8ce8-105">Este escenario es interoperable porque utiliza WS-Security con el perfil de token de certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-105">This scenario is interoperable because it uses WS-Security with the X.509 certificate token profile.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8ce8-106">Este escenario no realiza negociación del certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-106">This scenario does not perform negotiation of the service certificate.</span></span> <span data-ttu-id="f8ce8-107">El certificado del servicio debe ser proporcionado de antemano al cliente de cualquier comunicación.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-107">The service certificate must be provided to the client in advance of any communication.</span></span> <span data-ttu-id="f8ce8-108">El certificado de servidor se puede distribuir con la aplicación o puede ser proporcionado en una comunicación fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-108">The server certificate can be distributed with the application or provided in an out-of-band communication.</span></span>  
  
 <span data-ttu-id="f8ce8-109">![Modo de seguridad con certificados mutuos](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span><span class="sxs-lookup"><span data-stu-id="f8ce8-109">![Message security with mutual certificates](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span></span>  
  
|<span data-ttu-id="f8ce8-110">Característica</span><span class="sxs-lookup"><span data-stu-id="f8ce8-110">Characteristic</span></span>|<span data-ttu-id="f8ce8-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8ce8-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="f8ce8-112">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="f8ce8-112">Security Mode</span></span>|<span data-ttu-id="f8ce8-113">Mensaje</span><span class="sxs-lookup"><span data-stu-id="f8ce8-113">Message</span></span>|  
|<span data-ttu-id="f8ce8-114">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="f8ce8-114">Interoperability</span></span>|<span data-ttu-id="f8ce8-115">Sí, clientes y servicios compatibles con WS-Security y el perfil de token de certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-115">Yes, with WS-Security and X.509 certificate token profile compatible clients and services.</span></span>|  
|<span data-ttu-id="f8ce8-116">Autenticación</span><span class="sxs-lookup"><span data-stu-id="f8ce8-116">Authentication</span></span>|<span data-ttu-id="f8ce8-117">Autenticación mutua del servidor y el cliente.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-117">Mutual authentication of the server and client.</span></span>|  
|<span data-ttu-id="f8ce8-118">Integridad</span><span class="sxs-lookup"><span data-stu-id="f8ce8-118">Integrity</span></span>|<span data-ttu-id="f8ce8-119">Sí</span><span class="sxs-lookup"><span data-stu-id="f8ce8-119">Yes</span></span>|  
|<span data-ttu-id="f8ce8-120">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="f8ce8-120">Confidentiality</span></span>|<span data-ttu-id="f8ce8-121">Sí</span><span class="sxs-lookup"><span data-stu-id="f8ce8-121">Yes</span></span>|  
|<span data-ttu-id="f8ce8-122">Transporte</span><span class="sxs-lookup"><span data-stu-id="f8ce8-122">Transport</span></span>|<span data-ttu-id="f8ce8-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="f8ce8-123">HTTP</span></span>|  
|<span data-ttu-id="f8ce8-124">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f8ce8-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="f8ce8-125">web de Office</span><span class="sxs-lookup"><span data-stu-id="f8ce8-125">Service</span></span>  
 <span data-ttu-id="f8ce8-126">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="f8ce8-127">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f8ce8-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="f8ce8-128">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="f8ce8-129">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f8ce8-130">Código</span><span class="sxs-lookup"><span data-stu-id="f8ce8-130">Code</span></span>  
 <span data-ttu-id="f8ce8-131">El código siguiente muestra cómo crear un punto de conexión de servicio que utilice la seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-131">The following code shows creates a service endpoint that uses message security.</span></span> <span data-ttu-id="f8ce8-132">El servicio exige a un certificado que se autentique.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-132">The service requires a certificate to authenticate itself.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#13)]
 [!code-vb[C_SecurityScenarios#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#13)]  
  
### <a name="configuration"></a><span data-ttu-id="f8ce8-133">Configuración</span><span class="sxs-lookup"><span data-stu-id="f8ce8-133">Configuration</span></span>  
 <span data-ttu-id="f8ce8-134">La configuración siguiente se puede utilizar en lugar del código para crear el mismo servicio.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-134">The following configuration can be used instead of the code to create the same service.</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="f8ce8-135">Cliente</span><span class="sxs-lookup"><span data-stu-id="f8ce8-135">Client</span></span>  
 <span data-ttu-id="f8ce8-136">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="f8ce8-137">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f8ce8-137">Do one of the following:</span></span>  
  
-   <span data-ttu-id="f8ce8-138">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="f8ce8-138">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="f8ce8-139">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="f8ce8-140">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="f8ce8-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f8ce8-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="f8ce8-142">Código</span><span class="sxs-lookup"><span data-stu-id="f8ce8-142">Code</span></span>  
 <span data-ttu-id="f8ce8-143">El siguiente código crea el cliente.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-143">The following code creates the client.</span></span> <span data-ttu-id="f8ce8-144">El modo de seguridad se establece en mensaje, y el tipo de credencial de cliente se establece en certificado.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-144">The security mode is set to Message, and the client credential type is set to Certificate.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#20)]
 [!code-vb[C_SecurityScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#20)]  
  
### <a name="configuration"></a><span data-ttu-id="f8ce8-145">Configuración</span><span class="sxs-lookup"><span data-stu-id="f8ce8-145">Configuration</span></span>  
 <span data-ttu-id="f8ce8-146">Lo siguiente configura el cliente.</span><span class="sxs-lookup"><span data-stu-id="f8ce8-146">The following configures the client.</span></span> <span data-ttu-id="f8ce8-147">Se debe especificar un certificado de cliente mediante el [ \<clientCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="f8ce8-147">A client certificate must be specified using the [\<clientCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span> <span data-ttu-id="f8ce8-148">Además, el certificado del servicio se especifica utilizando el [ \<defaultCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="f8ce8-148">Also, the service certificate is specified using the [\<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f8ce8-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8ce8-149">See also</span></span>

- [<span data-ttu-id="f8ce8-150">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="f8ce8-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="f8ce8-151">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="f8ce8-151">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
- [<span data-ttu-id="f8ce8-152">Cómo: Crear e instalar certificados temporales en WCF para la seguridad de transporte durante el desarrollo</span><span class="sxs-lookup"><span data-stu-id="f8ce8-152">How to: Create and Install Temporary Certificates in WCF for Transport Security During Development</span></span>](https://go.microsoft.com/fwlink/?LinkId=244264)
