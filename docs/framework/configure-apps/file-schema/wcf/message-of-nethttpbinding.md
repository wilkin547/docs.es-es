---
title: <message> de <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 62b1793d18ddc8edc1f55b02137c4e0a9f7327d2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738962"
---
# <a name="message-of-nethttpbinding"></a><span data-ttu-id="3da92-102">\<message> de \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="3da92-102">\<message> of \<netHttpBinding></span></span>
<span data-ttu-id="3da92-103">Define la configuración para la seguridad de nivel de mensaje de [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="3da92-103">Defines the settings for message-level security of the [\<netHttpBinding>](nethttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="3da92-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3da92-104">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3da92-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3da92-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3da92-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3da92-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3da92-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="3da92-107">Attributes</span></span>  
  
|<span data-ttu-id="3da92-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="3da92-108">Attribute</span></span>|<span data-ttu-id="3da92-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3da92-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3da92-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="3da92-110">algorithmSuite</span></span>|<span data-ttu-id="3da92-111">Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3da92-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="3da92-112">Este atributo es de tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, que especifica los algoritmos y los tamaños clave.</span><span class="sxs-lookup"><span data-stu-id="3da92-112">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="3da92-113">Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="3da92-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="3da92-114">El valor predeterminado es `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="3da92-114">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="3da92-115">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="3da92-115">clientCredentialType</span></span>|<span data-ttu-id="3da92-116">Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad basada en mensaje.</span><span class="sxs-lookup"><span data-stu-id="3da92-116">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="3da92-117">De manera predeterminada, es `UserName`.</span><span class="sxs-lookup"><span data-stu-id="3da92-117">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="3da92-118">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="3da92-118">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="3da92-119">Value</span><span class="sxs-lookup"><span data-stu-id="3da92-119">Value</span></span>|<span data-ttu-id="3da92-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="3da92-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3da92-121">UserName</span><span class="sxs-lookup"><span data-stu-id="3da92-121">UserName</span></span>|<span data-ttu-id="3da92-122">-Requiere que el cliente se autentique en el servidor con una credencial de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="3da92-122">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="3da92-123">Esta credencial debe especificarse mediante el elemento <`clientCredentials`>.</span><span class="sxs-lookup"><span data-stu-id="3da92-123">This credential needs to be specified using the <`clientCredentials`> element.</span></span><br /><span data-ttu-id="3da92-124">-WCF no admite el envío de un resumen de contraseña ni la derivación de claves mediante contraseñas y el uso de tales claves para la seguridad de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="3da92-124">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="3da92-125">Por lo tanto, WCF exige que el transporte se proteja al utilizar las credenciales de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="3da92-125">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="3da92-126">Para `basicHttpBinding`, esto requiere configurar un canal de SSL.</span><span class="sxs-lookup"><span data-stu-id="3da92-126">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="3da92-127">Certificado</span><span class="sxs-lookup"><span data-stu-id="3da92-127">Certificate</span></span>|<span data-ttu-id="3da92-128">Exige la autenticación del cliente en el servidor mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="3da92-128">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="3da92-129">La credencial del cliente en este caso debe especificarse mediante <`clientCredentials`> y el `clientCertificate`> <.</span><span class="sxs-lookup"><span data-stu-id="3da92-129">The client credential in this case needs to be specified using <`clientCredentials`> and the <`clientCertificate`>.</span></span> <span data-ttu-id="3da92-130">Además, cuando se utiliza el modo de seguridad de mensajes, se debe proporcionar el cliente con el certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="3da92-130">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="3da92-131">En este caso, la credencial de servicio debe especificarse mediante <xref:System.ServiceModel.Description.ClientCredentials> `ClientCredentials` el elemento Class o Behavior y especificando el certificado de servicio mediante el \<serviceCertificate> elemento de serviceCredentials.</span><span class="sxs-lookup"><span data-stu-id="3da92-131">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the \<serviceCertificate> element of serviceCredentials.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3da92-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3da92-132">Child Elements</span></span>  
 <span data-ttu-id="3da92-133">None</span><span class="sxs-lookup"><span data-stu-id="3da92-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3da92-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3da92-134">Parent Elements</span></span>  
  
|<span data-ttu-id="3da92-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="3da92-135">Element</span></span>|<span data-ttu-id="3da92-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="3da92-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3da92-137"><`security`> elemento de <`netHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="3da92-137"><`security`> element of <`netHttpBinding`></span></span>|<span data-ttu-id="3da92-138">Define las funciones de seguridad para el `netHttpBinding` elemento> de <.</span><span class="sxs-lookup"><span data-stu-id="3da92-138">Defines the security capabilities for the <`netHttpBinding`> Element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3da92-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3da92-139">Example</span></span>  
 <span data-ttu-id="3da92-140">Este ejemplo muestra cómo implementar una aplicación que utiliza basicHttpBinding y modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3da92-140">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="3da92-141">En el ejemplo de configuración de un servicio siguiente, la definición de extremo especifica basicHttpBinding y hace referencia a una configuración de enlace denominada `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="3da92-141">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="3da92-142">El certificado que el servicio utiliza para autenticarse al cliente se establece en la sección `behaviors` del archivo de configuración bajo el elemento `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="3da92-142">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="3da92-143">El modo de la validación que se aplica al certificado que el cliente utiliza para autenticarse al servicio también se establece en la sección `behaviors` bajo el elemento `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="3da92-143">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="3da92-144">El mismo enlace y detalles de seguridad se especifican en el archivo de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="3da92-144">The same binding and security details are specified in the client configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3da92-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3da92-145">See also</span></span>

- [<span data-ttu-id="3da92-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3da92-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3da92-147">Enlaces</span><span class="sxs-lookup"><span data-stu-id="3da92-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3da92-148">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="3da92-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3da92-149">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3da92-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
