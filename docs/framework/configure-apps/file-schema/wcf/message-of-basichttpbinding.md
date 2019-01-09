---
title: Elemento &lt;message&gt; de &lt;basicHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 51cdd329-6461-471a-8747-56c2299b61e5
ms.openlocfilehash: 8c3519e2db12e34d9f2bd03689e0e9684c5792ae
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151285"
---
# <a name="ltmessagegt-of-ltbasichttpbindinggt"></a><span data-ttu-id="53641-102">Elemento &lt;message&gt; de &lt;basicHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="53641-102">&lt;message&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="53641-103">Define la configuración de seguridad de nivel de mensaje de la [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="53641-103">Defines the settings for message-level security of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="53641-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="53641-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="53641-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="53641-105">\<bindings></span></span>  
<span data-ttu-id="53641-106">\<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="53641-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="53641-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="53641-107">\<binding></span></span>  
<span data-ttu-id="53641-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="53641-108">\<security></span></span>  
<span data-ttu-id="53641-109">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="53641-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53641-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53641-110">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53641-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="53641-111">Attributes and Elements</span></span>  
 <span data-ttu-id="53641-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="53641-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53641-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="53641-113">Attributes</span></span>  
  
|<span data-ttu-id="53641-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="53641-114">Attribute</span></span>|<span data-ttu-id="53641-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="53641-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53641-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="53641-116">algorithmSuite</span></span>|<span data-ttu-id="53641-117">Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="53641-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="53641-118">Este atributo es de tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, que especifica los algoritmos y los tamaños clave.</span><span class="sxs-lookup"><span data-stu-id="53641-118">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="53641-119">Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="53641-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="53641-120">El valor predeterminado es `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="53641-120">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="53641-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="53641-121">clientCredentialType</span></span>|<span data-ttu-id="53641-122">Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad basada en mensaje.</span><span class="sxs-lookup"><span data-stu-id="53641-122">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="53641-123">De manera predeterminada, es `UserName`.</span><span class="sxs-lookup"><span data-stu-id="53641-123">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="53641-124">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="53641-124">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="53641-125">Valor</span><span class="sxs-lookup"><span data-stu-id="53641-125">Value</span></span>|<span data-ttu-id="53641-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="53641-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53641-127">UserName</span><span class="sxs-lookup"><span data-stu-id="53641-127">UserName</span></span>|<span data-ttu-id="53641-128">-Requiere la autenticación del cliente al servidor con una credencial UserName.</span><span class="sxs-lookup"><span data-stu-id="53641-128">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="53641-129">Esta credencial debe especificarse utilizando la [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).</span><span class="sxs-lookup"><span data-stu-id="53641-129">This credential needs to be specified using the [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).</span></span><br /><span data-ttu-id="53641-130">-WCF no admite enviar un resumen de contraseña ni derivar claves mediante contraseñas y utilizando tales claves para seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="53641-130">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="53641-131">Por lo tanto, WCF impone que el transporte sea seguro al usar credenciales UserName.</span><span class="sxs-lookup"><span data-stu-id="53641-131">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="53641-132">Para `basicHttpBinding`, esto requiere configurar un canal de SSL.</span><span class="sxs-lookup"><span data-stu-id="53641-132">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="53641-133">Certificado</span><span class="sxs-lookup"><span data-stu-id="53641-133">Certificate</span></span>|<span data-ttu-id="53641-134">Exige la autenticación del cliente en el servidor mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="53641-134">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="53641-135">La credencial del cliente en este caso necesita ser especificada utilizando [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) y [ \<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="53641-135">The client credential in this case needs to be specified using [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) and the [\<clientCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md).</span></span> <span data-ttu-id="53641-136">Además, cuando se utiliza el modo de seguridad de mensajes, se debe proporcionar el cliente con el certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="53641-136">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="53641-137">La credencial del servicio en este caso necesita ser especificada utilizando <xref:System.ServiceModel.Description.ClientCredentials> clase o `ClientCredentials` elemento de comportamiento especificando el servicio de certificado mediante el [ \<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="53641-137">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the [\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53641-138">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="53641-138">Child Elements</span></span>  
 <span data-ttu-id="53641-139">Ninguna</span><span class="sxs-lookup"><span data-stu-id="53641-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53641-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="53641-140">Parent Elements</span></span>  
  
|<span data-ttu-id="53641-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="53641-141">Element</span></span>|<span data-ttu-id="53641-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="53641-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53641-143">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="53641-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="53641-144">Define las funciones de seguridad para el [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="53641-144">Defines the security capabilities for the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="53641-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53641-145">Example</span></span>  
 <span data-ttu-id="53641-146">Este ejemplo muestra cómo implementar una aplicación que utiliza basicHttpBinding y modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="53641-146">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="53641-147">En el ejemplo de configuración de un servicio siguiente, la definición de extremo especifica basicHttpBinding y hace referencia a una configuración de enlace denominada `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="53641-147">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="53641-148">El certificado que el servicio utiliza para autenticarse al cliente se establece en la sección `behaviors` del archivo de configuración bajo el elemento `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="53641-148">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="53641-149">El modo de la validación que se aplica al certificado que el cliente utiliza para autenticarse al servicio también se establece en la sección `behaviors` bajo el elemento `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="53641-149">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="53641-150">El mismo enlace y detalles de seguridad se especifican en el archivo de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="53641-150">The same binding and security details are specified in the client configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service -->
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
    <!-- This configuration defines the SecurityMode as Message and
         the clientCredentialType as Certificate. -->
      <binding name="Binding1">
        <security mode = "Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True" />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <!-- The serviceCredentials behavior allows one to define a service certificate.
             A service certificate is used by a client to authenticate the service and provide message protection.
             This configuration references the "localhost" certificate installed during the setup instructions. -->
        <serviceCredentials>
          <serviceCertificate findValue="localhost"
                              storeLocation="LocalMachine"
                              storeName="My"
                              x509FindType="FindBySubjectName" />
          <clientCertificate>
            <!-- Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
               is in the user's Trusted People store, then it will be trusted without performing a
               validation of the certificate's issuer chain. This setting is used here for convenience so that the
               sample can be run without having to have certificates issued by a certification authority (CA).
               This setting is less secure than the default, ChainTrust. The security implications of this
               setting should be carefully considered before using PeerOrChainTrust in production code. -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="53641-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="53641-151">See Also</span></span>  
 <xref:System.ServiceModel.BasicHttpMessageSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.BasicHttpSecurity.Message%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpMessageSecurityElement>  
 [<span data-ttu-id="53641-152">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="53641-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="53641-153">Enlaces</span><span class="sxs-lookup"><span data-stu-id="53641-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="53641-154">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="53641-154">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="53641-155">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="53641-155">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="53641-156">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="53641-156">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
