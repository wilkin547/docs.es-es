---
title: <message> de <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 51cdd329-6461-471a-8747-56c2299b61e5
ms.openlocfilehash: bce80d96b1bcec0d580f2de3fe88d5fd6ad0a3b5
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400265"
---
# <a name="message-of-basichttpbinding"></a><span data-ttu-id="8ec20-102">\<> de mensajes \<de basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="8ec20-102">\<message> of \<basicHttpBinding></span></span>
<span data-ttu-id="8ec20-103">Define la configuración para la [ \<](basichttpbinding.md)seguridad de nivel de mensaje del > basicHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="8ec20-103">Defines the settings for message-level security of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
<span data-ttu-id="8ec20-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8ec20-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8ec20-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8ec20-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8ec20-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="8ec20-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8ec20-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> basicHttpBinding**](basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8ec20-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="8ec20-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="8ec20-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8ec20-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8ec20-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-basichttpbinding.md)</span></span>\
<span data-ttu-id="8ec20-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de mensajes**</span><span class="sxs-lookup"><span data-stu-id="8ec20-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ec20-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ec20-111">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ec20-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8ec20-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8ec20-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8ec20-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ec20-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="8ec20-114">Attributes</span></span>  
  
|<span data-ttu-id="8ec20-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="8ec20-115">Attribute</span></span>|<span data-ttu-id="8ec20-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8ec20-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ec20-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="8ec20-117">algorithmSuite</span></span>|<span data-ttu-id="8ec20-118">Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8ec20-118">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="8ec20-119">Este atributo es de tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, que especifica los algoritmos y los tamaños clave.</span><span class="sxs-lookup"><span data-stu-id="8ec20-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="8ec20-120">Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="8ec20-120">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="8ec20-121">El valor predeterminado es `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="8ec20-121">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="8ec20-122">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8ec20-122">clientCredentialType</span></span>|<span data-ttu-id="8ec20-123">Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad basada en mensaje.</span><span class="sxs-lookup"><span data-stu-id="8ec20-123">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="8ec20-124">El valor predeterminado es `UserName`.</span><span class="sxs-lookup"><span data-stu-id="8ec20-124">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="8ec20-125">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8ec20-125">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="8ec20-126">Valor</span><span class="sxs-lookup"><span data-stu-id="8ec20-126">Value</span></span>|<span data-ttu-id="8ec20-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8ec20-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8ec20-128">UserName</span><span class="sxs-lookup"><span data-stu-id="8ec20-128">UserName</span></span>|<span data-ttu-id="8ec20-129">-Requiere que el cliente se autentique en el servidor con una credencial de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="8ec20-129">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="8ec20-130">Esta credencial debe especificarse mediante el [ \<> clientCredentials](clientcredentials.md).</span><span class="sxs-lookup"><span data-stu-id="8ec20-130">This credential needs to be specified using the [\<clientCredentials>](clientcredentials.md).</span></span><br /><span data-ttu-id="8ec20-131">-WCF no admite el envío de un resumen de contraseña ni la derivación de claves mediante contraseñas y el uso de tales claves para la seguridad de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="8ec20-131">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="8ec20-132">Por lo tanto, WCF exige que el transporte se proteja al utilizar las credenciales de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="8ec20-132">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="8ec20-133">Para `basicHttpBinding`, esto requiere configurar un canal de SSL.</span><span class="sxs-lookup"><span data-stu-id="8ec20-133">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="8ec20-134">Certificate</span><span class="sxs-lookup"><span data-stu-id="8ec20-134">Certificate</span></span>|<span data-ttu-id="8ec20-135">Exige la autenticación del cliente en el servidor mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="8ec20-135">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="8ec20-136">La credencial del cliente en este caso debe especificarse con [ \<el > clientCredentials](clientcredentials.md) y el [ \<> clientCertificate](clientcertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="8ec20-136">The client credential in this case needs to be specified using [\<clientCredentials>](clientcredentials.md) and the [\<clientCertificate>](clientcertificate-of-servicecredentials.md).</span></span> <span data-ttu-id="8ec20-137">Además, cuando se utiliza el modo de seguridad de mensajes, se debe proporcionar el cliente con el certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="8ec20-137">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="8ec20-138">En este caso, la credencial de servicio debe especificarse <xref:System.ServiceModel.Description.ClientCredentials> mediante el `ClientCredentials` elemento Class o Behavior y especificando el certificado de servicio mediante el [ \<> serviceCertificate](servicecertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="8ec20-138">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the [\<serviceCertificate>](servicecertificate-of-servicecredentials.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ec20-139">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8ec20-139">Child Elements</span></span>  
 <span data-ttu-id="8ec20-140">None</span><span class="sxs-lookup"><span data-stu-id="8ec20-140">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ec20-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8ec20-141">Parent Elements</span></span>  
  
|<span data-ttu-id="8ec20-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="8ec20-142">Element</span></span>|<span data-ttu-id="8ec20-143">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8ec20-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ec20-144">\<security></span><span class="sxs-lookup"><span data-stu-id="8ec20-144">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="8ec20-145">Define las funciones de seguridad para el [ \<> basicHttpBinding](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8ec20-145">Defines the security capabilities for the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8ec20-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ec20-146">Example</span></span>  
 <span data-ttu-id="8ec20-147">Este ejemplo muestra cómo implementar una aplicación que utiliza basicHttpBinding y modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8ec20-147">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="8ec20-148">En el ejemplo de configuración de un servicio siguiente, la definición de extremo especifica basicHttpBinding y hace referencia a una configuración de enlace denominada `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="8ec20-148">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="8ec20-149">El certificado que el servicio utiliza para autenticarse al cliente se establece en la sección `behaviors` del archivo de configuración bajo el elemento `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="8ec20-149">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="8ec20-150">El modo de la validación que se aplica al certificado que el cliente utiliza para autenticarse al servicio también se establece en la sección `behaviors` bajo el elemento `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="8ec20-150">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="8ec20-151">El mismo enlace y detalles de seguridad se especifican en el archivo de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="8ec20-151">The same binding and security details are specified in the client configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8ec20-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ec20-152">See also</span></span>

- <xref:System.ServiceModel.BasicHttpMessageSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpMessageSecurityElement>
- [<span data-ttu-id="8ec20-153">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8ec20-153">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8ec20-154">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8ec20-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8ec20-155">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="8ec20-155">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8ec20-156">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8ec20-156">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8ec20-157">\<binding></span><span class="sxs-lookup"><span data-stu-id="8ec20-157">\<binding></span></span>](../../../misc/binding.md)
