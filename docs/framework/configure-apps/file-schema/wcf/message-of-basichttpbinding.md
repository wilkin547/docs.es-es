---
title: Elemento &lt;message&gt; de &lt;basicHttpBinding&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51cdd329-6461-471a-8747-56c2299b61e5
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 791e5c57991fb9fe616cfaa18b475b2ea93dc965
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltmessagegt-of-ltbasichttpbindinggt"></a><span data-ttu-id="88be0-102">Elemento &lt;message&gt; de &lt;basicHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="88be0-102">&lt;message&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="88be0-103">Define la configuración de seguridad de nivel de mensaje de la [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="88be0-103">Defines the settings for message-level security of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="88be0-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="88be0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="88be0-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="88be0-105">\<bindings></span></span>  
<span data-ttu-id="88be0-106">\<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="88be0-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="88be0-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="88be0-107">\<binding></span></span>  
<span data-ttu-id="88be0-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="88be0-108">\<security></span></span>  
<span data-ttu-id="88be0-109">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="88be0-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88be0-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88be0-110">Syntax</span></span>  
  
```xml  
<message   
   algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="UserName/Certificate"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88be0-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="88be0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="88be0-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="88be0-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88be0-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="88be0-113">Attributes</span></span>  
  
|<span data-ttu-id="88be0-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="88be0-114">Attribute</span></span>|<span data-ttu-id="88be0-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="88be0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88be0-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="88be0-116">algorithmSuite</span></span>|<span data-ttu-id="88be0-117">Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="88be0-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="88be0-118">Este atributo es de tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, que especifica los algoritmos y los tamaños clave.</span><span class="sxs-lookup"><span data-stu-id="88be0-118">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="88be0-119">Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="88be0-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="88be0-120">El valor predeterminado es `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="88be0-120">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="88be0-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="88be0-121">clientCredentialType</span></span>|<span data-ttu-id="88be0-122">Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad basada en mensaje.</span><span class="sxs-lookup"><span data-stu-id="88be0-122">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="88be0-123">De manera predeterminada, es `UserName`.</span><span class="sxs-lookup"><span data-stu-id="88be0-123">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="88be0-124">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="88be0-124">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="88be0-125">Valor</span><span class="sxs-lookup"><span data-stu-id="88be0-125">Value</span></span>|<span data-ttu-id="88be0-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="88be0-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="88be0-127">UserName</span><span class="sxs-lookup"><span data-stu-id="88be0-127">UserName</span></span>|<span data-ttu-id="88be0-128">-Requiere la autenticación del cliente en el servidor con una credencial de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="88be0-128">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="88be0-129">Esta credencial se tiene que especificarse con el [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).</span><span class="sxs-lookup"><span data-stu-id="88be0-129">This credential needs to be specified using the [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).</span></span><br /><span data-ttu-id="88be0-130">-   [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]no admite enviar un resumen de contraseña ni derivar claves mediante contraseñas y utilizar tales claves para seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="88be0-130">-   [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="88be0-131">Por lo tanto, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] garantiza que el transporte sea seguro al usar credenciales UserName.</span><span class="sxs-lookup"><span data-stu-id="88be0-131">Therefore, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="88be0-132">Para `basicHttpBinding`, esto requiere configurar un canal de SSL.</span><span class="sxs-lookup"><span data-stu-id="88be0-132">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="88be0-133">Certificado</span><span class="sxs-lookup"><span data-stu-id="88be0-133">Certificate</span></span>|<span data-ttu-id="88be0-134">Exige la autenticación del cliente en el servidor mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="88be0-134">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="88be0-135">La credencial del cliente en este caso debe especificarse mediante [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) y [ \<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="88be0-135">The client credential in this case needs to be specified using [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) and the [\<clientCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md).</span></span> <span data-ttu-id="88be0-136">Además, cuando se utiliza el modo de seguridad de mensajes, se debe proporcionar el cliente con el certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="88be0-136">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="88be0-137">La credencial de servicio en este caso debe especificarse mediante <xref:System.ServiceModel.Description.ClientCredentials> clase o `ClientCredentials` elemento de comportamiento y especificar el servicio de certificados utilizando el [ \<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="88be0-137">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the [\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88be0-138">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="88be0-138">Child Elements</span></span>  
 <span data-ttu-id="88be0-139">Ninguna</span><span class="sxs-lookup"><span data-stu-id="88be0-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88be0-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="88be0-140">Parent Elements</span></span>  
  
|<span data-ttu-id="88be0-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="88be0-141">Element</span></span>|<span data-ttu-id="88be0-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="88be0-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88be0-143">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="88be0-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="88be0-144">Define las funciones de seguridad para la [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="88be0-144">Defines the security capabilities for the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="88be0-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88be0-145">Example</span></span>  
 <span data-ttu-id="88be0-146">Este ejemplo muestra cómo implementar una aplicación que utiliza basicHttpBinding y modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="88be0-146">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="88be0-147">En el ejemplo de configuración de un servicio siguiente, la definición de extremo especifica basicHttpBinding y hace referencia a una configuración de enlace denominada `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="88be0-147">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="88be0-148">El certificado que el servicio utiliza para autenticarse al cliente se establece en la sección `behaviors` del archivo de configuración bajo el elemento `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="88be0-148">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="88be0-149">El modo de la validación que se aplica al certificado que el cliente utiliza para autenticarse al servicio también se establece en la sección `behaviors` bajo el elemento `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="88be0-149">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="88be0-150">El mismo enlace y detalles de seguridad se especifican en el archivo de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="88be0-150">The same binding and security details are specified in the client configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->  
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
        <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1" >  
          <security mode = "Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--  
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by a client to authenticate the service and provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="88be0-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="88be0-151">See Also</span></span>  
 <xref:System.ServiceModel.BasicHttpMessageSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.BasicHttpSecurity.Message%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpMessageSecurityElement>  
 [<span data-ttu-id="88be0-152">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="88be0-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="88be0-153">Enlaces</span><span class="sxs-lookup"><span data-stu-id="88be0-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="88be0-154">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="88be0-154">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="88be0-155">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="88be0-155">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="88be0-156">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="88be0-156">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
