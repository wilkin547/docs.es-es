---
title: Seguridad de mensajes con un cliente de certificado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99770573-c815-4428-a38c-e4335c8bd7ce
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 570c7763da912de4e0d2729e7579a200f35c4941
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494698"
---
# <a name="message-security-with-a-certificate-client"></a><span data-ttu-id="7822d-102">Seguridad de mensajes con un cliente de certificado</span><span class="sxs-lookup"><span data-stu-id="7822d-102">Message Security with a Certificate Client</span></span>
<span data-ttu-id="7822d-103">El escenario siguiente muestra un cliente de Windows Communication Foundation (WCF) y el servicio protegido utilizando el modo de seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="7822d-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured using message security mode.</span></span> <span data-ttu-id="7822d-104">Tanto el cliente como el servicio se autentican con certificados.</span><span class="sxs-lookup"><span data-stu-id="7822d-104">Both the client and the service are authenticated with certificates.</span></span> <span data-ttu-id="7822d-105">Para obtener más información, consulte [seguridad de las aplicaciones distribuidas](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span><span class="sxs-lookup"><span data-stu-id="7822d-105">For more information, see [Distributed Application Security](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span></span>  
  
 <span data-ttu-id="7822d-106">Para una aplicación de ejemplo, vea [certificado de seguridad de mensaje](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="7822d-106">For a sample application, see [Message Security Certificate](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span></span>  
  
 <span data-ttu-id="7822d-107">![Cliente con certificado](../../../../docs/framework/wcf/feature-details/media/clientwithcertificate.gif "ClientWithCertificate")</span><span class="sxs-lookup"><span data-stu-id="7822d-107">![Client with certificate](../../../../docs/framework/wcf/feature-details/media/clientwithcertificate.gif "ClientWithCertificate")</span></span>  
  
|<span data-ttu-id="7822d-108">Característica</span><span class="sxs-lookup"><span data-stu-id="7822d-108">Characteristic</span></span>|<span data-ttu-id="7822d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7822d-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7822d-110">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="7822d-110">Security Mode</span></span>|<span data-ttu-id="7822d-111">Mensaje</span><span class="sxs-lookup"><span data-stu-id="7822d-111">Message</span></span>|  
|<span data-ttu-id="7822d-112">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="7822d-112">Interoperability</span></span>|<span data-ttu-id="7822d-113">WCF solo</span><span class="sxs-lookup"><span data-stu-id="7822d-113">WCF only</span></span>|  
|<span data-ttu-id="7822d-114">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="7822d-114">Authentication (Server)</span></span>|<span data-ttu-id="7822d-115">Con el certificado del servicio</span><span class="sxs-lookup"><span data-stu-id="7822d-115">Using service certificate</span></span>|  
|<span data-ttu-id="7822d-116">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="7822d-116">Authentication (Client)</span></span>|<span data-ttu-id="7822d-117">Con el certificado del cliente</span><span class="sxs-lookup"><span data-stu-id="7822d-117">Using client certificate</span></span>|  
|<span data-ttu-id="7822d-118">Integridad</span><span class="sxs-lookup"><span data-stu-id="7822d-118">Integrity</span></span>|<span data-ttu-id="7822d-119">Sí</span><span class="sxs-lookup"><span data-stu-id="7822d-119">Yes</span></span>|  
|<span data-ttu-id="7822d-120">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="7822d-120">Confidentiality</span></span>|<span data-ttu-id="7822d-121">Sí</span><span class="sxs-lookup"><span data-stu-id="7822d-121">Yes</span></span>|  
|<span data-ttu-id="7822d-122">Transporte</span><span class="sxs-lookup"><span data-stu-id="7822d-122">Transport</span></span>|<span data-ttu-id="7822d-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="7822d-123">HTTP</span></span>|  
|<span data-ttu-id="7822d-124">Enlaces</span><span class="sxs-lookup"><span data-stu-id="7822d-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="7822d-125">Servicio</span><span class="sxs-lookup"><span data-stu-id="7822d-125">Service</span></span>  
 <span data-ttu-id="7822d-126">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="7822d-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="7822d-127">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7822d-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="7822d-128">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="7822d-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="7822d-129">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún extremo.</span><span class="sxs-lookup"><span data-stu-id="7822d-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7822d-130">Código</span><span class="sxs-lookup"><span data-stu-id="7822d-130">Code</span></span>  
 <span data-ttu-id="7822d-131">El código siguiente muestra cómo crear un punto de conexión de servicio que utilice la seguridad del mensaje para establecer un contexto seguro.</span><span class="sxs-lookup"><span data-stu-id="7822d-131">The following code shows how to create a service endpoint that uses message security to establish a secure context.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#10)]
 [!code-vb[C_SecurityScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#10)]  
  
### <a name="configuration"></a><span data-ttu-id="7822d-132">Configuración</span><span class="sxs-lookup"><span data-stu-id="7822d-132">Configuration</span></span>  
 <span data-ttu-id="7822d-133">En lugar del código, se puede utilizar la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="7822d-133">The following configuration can be used instead of the code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndCerficiateClient"   
                  name="SecuredByClientCertificate"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="7822d-134">Cliente</span><span class="sxs-lookup"><span data-stu-id="7822d-134">Client</span></span>  
 <span data-ttu-id="7822d-135">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="7822d-135">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="7822d-136">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7822d-136">Do one of the following:</span></span>  
  
-   <span data-ttu-id="7822d-137">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="7822d-137">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="7822d-138">Cree un cliente que no defina direcciones de extremo.</span><span class="sxs-lookup"><span data-stu-id="7822d-138">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="7822d-139">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="7822d-139">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="7822d-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7822d-140">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="7822d-141">Código</span><span class="sxs-lookup"><span data-stu-id="7822d-141">Code</span></span>  
 <span data-ttu-id="7822d-142">El siguiente código crea el cliente.</span><span class="sxs-lookup"><span data-stu-id="7822d-142">The following code creates the client.</span></span> <span data-ttu-id="7822d-143">El enlace es para la seguridad del modo de mensaje y el tipo de credencial de cliente está establecido en `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="7822d-143">The binding is to message mode security, and the client credential type is set to `Certificate`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#17)]
 [!code-vb[C_SecurityScenarios#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#17)]  
  
### <a name="configuration"></a><span data-ttu-id="7822d-144">Configuración</span><span class="sxs-lookup"><span data-stu-id="7822d-144">Configuration</span></span>  
 <span data-ttu-id="7822d-145">La configuración siguiente especifica el certificado de cliente mediante un comportamiento del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7822d-145">The following configuration specifies the client certificate using an endpoint behavior.</span></span> <span data-ttu-id="7822d-146">Para más información, consulte [Trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="7822d-146">For more information about certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="7822d-147">El código también usa una <`identity`> elemento para especificar un sistema de nombres de dominio (DNS) de la identidad del servidor esperado.</span><span class="sxs-lookup"><span data-stu-id="7822d-147">The code also uses an <`identity`> element to specify a Domain Name System (DNS) of the expected server identity.</span></span> <span data-ttu-id="7822d-148">Para obtener más información acerca de la identidad, vea [autenticación e identidad de servicio](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="7822d-148">For more information about identity, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"   
               storeLocation="LocalMachine"  
              x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                behaviorConfiguration="endpointCredentialsBehavior"  
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7822d-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="7822d-149">See Also</span></span>  
 [<span data-ttu-id="7822d-150">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="7822d-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="7822d-151">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="7822d-151">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="7822d-152">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="7822d-152">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="7822d-153">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="7822d-153">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
