---
title: <message> de <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 62b1793d18ddc8edc1f55b02137c4e0a9f7327d2
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738962"
---
# <a name="message-of-nethttpbinding"></a><span data-ttu-id="af76d-102">\<> de mensajes de \<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="af76d-102">\<message> of \<netHttpBinding></span></span>
<span data-ttu-id="af76d-103">Define la configuración para la seguridad de nivel de mensaje del [\<netHttpBinding >](nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="af76d-103">Defines the settings for message-level security of the [\<netHttpBinding>](nethttpbinding.md).</span></span>  
  
<span data-ttu-id="af76d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="af76d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="af76d-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="af76d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="af76d-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="af76d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="af76d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding**](nethttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="af76d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="af76d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="af76d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="af76d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**seguridad**](security-of-nethttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="af76d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)</span></span>\
<span data-ttu-id="af76d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**mensaje** ></span><span class="sxs-lookup"><span data-stu-id="af76d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af76d-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af76d-111">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af76d-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="af76d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="af76d-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="af76d-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af76d-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="af76d-114">Attributes</span></span>  
  
|<span data-ttu-id="af76d-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="af76d-115">Attribute</span></span>|<span data-ttu-id="af76d-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="af76d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af76d-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="af76d-117">algorithmSuite</span></span>|<span data-ttu-id="af76d-118">Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="af76d-118">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="af76d-119">Este atributo es de tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, que especifica los algoritmos y los tamaños clave.</span><span class="sxs-lookup"><span data-stu-id="af76d-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="af76d-120">Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="af76d-120">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="af76d-121">El valor predeterminado es `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="af76d-121">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="af76d-122">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="af76d-122">clientCredentialType</span></span>|<span data-ttu-id="af76d-123">Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad basada en mensaje.</span><span class="sxs-lookup"><span data-stu-id="af76d-123">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="af76d-124">De manera predeterminada, es `UserName`.</span><span class="sxs-lookup"><span data-stu-id="af76d-124">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="af76d-125">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="af76d-125">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="af76d-126">Valor</span><span class="sxs-lookup"><span data-stu-id="af76d-126">Value</span></span>|<span data-ttu-id="af76d-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="af76d-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="af76d-128">UserName</span><span class="sxs-lookup"><span data-stu-id="af76d-128">UserName</span></span>|<span data-ttu-id="af76d-129">-Requiere que el cliente se autentique en el servidor con una credencial de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="af76d-129">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="af76d-130">Esta credencial debe especificarse mediante el elemento de >`clientCredentials`de <.</span><span class="sxs-lookup"><span data-stu-id="af76d-130">This credential needs to be specified using the <`clientCredentials`> element.</span></span><br /><span data-ttu-id="af76d-131">-WCF no admite el envío de un resumen de contraseña ni la derivación de claves mediante contraseñas y el uso de tales claves para la seguridad de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="af76d-131">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="af76d-132">Por lo tanto, WCF exige que el transporte se proteja al utilizar las credenciales de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="af76d-132">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="af76d-133">Para `basicHttpBinding`, esto requiere configurar un canal de SSL.</span><span class="sxs-lookup"><span data-stu-id="af76d-133">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="af76d-134">Certificado</span><span class="sxs-lookup"><span data-stu-id="af76d-134">Certificate</span></span>|<span data-ttu-id="af76d-135">Exige la autenticación del cliente en el servidor mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="af76d-135">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="af76d-136">En este caso, la credencial de cliente debe especificarse mediante <`clientCredentials`> y el`clientCertificate`de > <.</span><span class="sxs-lookup"><span data-stu-id="af76d-136">The client credential in this case needs to be specified using <`clientCredentials`> and the <`clientCertificate`>.</span></span> <span data-ttu-id="af76d-137">Además, cuando se utiliza el modo de seguridad de mensajes, se debe proporcionar el cliente con el certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="af76d-137">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="af76d-138">En este caso, la credencial de servicio debe especificarse mediante <xref:System.ServiceModel.Description.ClientCredentials> clase o `ClientCredentials` elemento Behavior y especificando el certificado de servicio mediante el elemento \<serviceCertificate > de serviceCredentials.</span><span class="sxs-lookup"><span data-stu-id="af76d-138">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the \<serviceCertificate> element of serviceCredentials.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af76d-139">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="af76d-139">Child Elements</span></span>  
 <span data-ttu-id="af76d-140">Ninguno</span><span class="sxs-lookup"><span data-stu-id="af76d-140">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af76d-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="af76d-141">Parent Elements</span></span>  
  
|<span data-ttu-id="af76d-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="af76d-142">Element</span></span>|<span data-ttu-id="af76d-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="af76d-143">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="af76d-144"><`security`elemento > de <`netHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="af76d-144"><`security`> element of <`netHttpBinding`></span></span>|<span data-ttu-id="af76d-145">Define las capacidades de seguridad para el <`netHttpBinding`elemento >.</span><span class="sxs-lookup"><span data-stu-id="af76d-145">Defines the security capabilities for the <`netHttpBinding`> Element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="af76d-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af76d-146">Example</span></span>  
 <span data-ttu-id="af76d-147">Este ejemplo muestra cómo implementar una aplicación que utiliza basicHttpBinding y modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="af76d-147">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="af76d-148">En el ejemplo de configuración de un servicio siguiente, la definición de extremo especifica basicHttpBinding y hace referencia a una configuración de enlace denominada `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="af76d-148">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="af76d-149">El certificado que el servicio utiliza para autenticarse al cliente se establece en la sección `behaviors` del archivo de configuración bajo el elemento `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="af76d-149">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="af76d-150">El modo de la validación que se aplica al certificado que el cliente utiliza para autenticarse al servicio también se establece en la sección `behaviors` bajo el elemento `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="af76d-150">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="af76d-151">El mismo enlace y detalles de seguridad se especifican en el archivo de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="af76d-151">The same binding and security details are specified in the client configuration file.</span></span>  
  
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
      <!-- This configuration defines the SecurityMode as Message and
           the clientCredentialType as Certificate. -->
      <binding name="Binding1" >
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
  
## <a name="see-also"></a><span data-ttu-id="af76d-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="af76d-152">See also</span></span>

- [<span data-ttu-id="af76d-153">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="af76d-153">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="af76d-154">Enlaces</span><span class="sxs-lookup"><span data-stu-id="af76d-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="af76d-155">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="af76d-155">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="af76d-156">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="af76d-156">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="af76d-157">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="af76d-157">\<binding></span></span>](bindings.md)
