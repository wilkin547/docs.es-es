---
description: 'Más información sobre: <message> de <netHttpBinding>'
title: <message> de <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 508e58e58dbb298081a075588ddda87289c1a3d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749623"
---
# <a name="message-of-nethttpbinding"></a><span data-ttu-id="69d85-103">\<message> de \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="69d85-103">\<message> of \<netHttpBinding></span></span>

<span data-ttu-id="69d85-104">Define la configuración para la seguridad de nivel de mensaje de [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="69d85-104">Defines the settings for message-level security of the [\<netHttpBinding>](nethttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="69d85-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69d85-105">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69d85-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="69d85-106">Attributes and Elements</span></span>  

 <span data-ttu-id="69d85-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="69d85-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69d85-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="69d85-108">Attributes</span></span>  
  
|<span data-ttu-id="69d85-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="69d85-109">Attribute</span></span>|<span data-ttu-id="69d85-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="69d85-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="69d85-111">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="69d85-111">algorithmSuite</span></span>|<span data-ttu-id="69d85-112">Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="69d85-112">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="69d85-113">Este atributo es de tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, que especifica los algoritmos y los tamaños clave.</span><span class="sxs-lookup"><span data-stu-id="69d85-113">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="69d85-114">Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="69d85-114">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="69d85-115">El valor predeterminado es `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="69d85-115">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="69d85-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="69d85-116">clientCredentialType</span></span>|<span data-ttu-id="69d85-117">Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad basada en mensaje.</span><span class="sxs-lookup"><span data-stu-id="69d85-117">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="69d85-118">De manera predeterminada, es `UserName`.</span><span class="sxs-lookup"><span data-stu-id="69d85-118">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="69d85-119">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="69d85-119">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="69d85-120">Value</span><span class="sxs-lookup"><span data-stu-id="69d85-120">Value</span></span>|<span data-ttu-id="69d85-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="69d85-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="69d85-122">UserName</span><span class="sxs-lookup"><span data-stu-id="69d85-122">UserName</span></span>|<span data-ttu-id="69d85-123">-Requiere que el cliente se autentique en el servidor con una credencial de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="69d85-123">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="69d85-124">Esta credencial debe especificarse mediante el elemento <`clientCredentials`>.</span><span class="sxs-lookup"><span data-stu-id="69d85-124">This credential needs to be specified using the <`clientCredentials`> element.</span></span><br /><span data-ttu-id="69d85-125">-WCF no admite el envío de un resumen de contraseña ni la derivación de claves mediante contraseñas y el uso de tales claves para la seguridad de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="69d85-125">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="69d85-126">Por lo tanto, WCF exige que el transporte se proteja al utilizar las credenciales de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="69d85-126">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="69d85-127">Para `basicHttpBinding`, esto requiere configurar un canal de SSL.</span><span class="sxs-lookup"><span data-stu-id="69d85-127">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="69d85-128">Certificado</span><span class="sxs-lookup"><span data-stu-id="69d85-128">Certificate</span></span>|<span data-ttu-id="69d85-129">Exige la autenticación del cliente en el servidor mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="69d85-129">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="69d85-130">La credencial del cliente en este caso debe especificarse mediante <`clientCredentials`> y el `clientCertificate`> <.</span><span class="sxs-lookup"><span data-stu-id="69d85-130">The client credential in this case needs to be specified using <`clientCredentials`> and the <`clientCertificate`>.</span></span> <span data-ttu-id="69d85-131">Además, cuando se utiliza el modo de seguridad de mensajes, se debe proporcionar el cliente con el certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="69d85-131">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="69d85-132">En este caso, la credencial de servicio debe especificarse mediante <xref:System.ServiceModel.Description.ClientCredentials> `ClientCredentials` el elemento Class o Behavior y especificando el certificado de servicio mediante el \<serviceCertificate> elemento de serviceCredentials.</span><span class="sxs-lookup"><span data-stu-id="69d85-132">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the \<serviceCertificate> element of serviceCredentials.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69d85-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="69d85-133">Child Elements</span></span>  

 <span data-ttu-id="69d85-134">None</span><span class="sxs-lookup"><span data-stu-id="69d85-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69d85-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="69d85-135">Parent Elements</span></span>  
  
|<span data-ttu-id="69d85-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="69d85-136">Element</span></span>|<span data-ttu-id="69d85-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="69d85-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="69d85-138"><`security`> elemento de <`netHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="69d85-138"><`security`> element of <`netHttpBinding`></span></span>|<span data-ttu-id="69d85-139">Define las funciones de seguridad para el `netHttpBinding` elemento> de <.</span><span class="sxs-lookup"><span data-stu-id="69d85-139">Defines the security capabilities for the <`netHttpBinding`> Element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="69d85-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69d85-140">Example</span></span>  

 <span data-ttu-id="69d85-141">Este ejemplo muestra cómo implementar una aplicación que utiliza basicHttpBinding y modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="69d85-141">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="69d85-142">En el ejemplo de configuración de un servicio siguiente, la definición de extremo especifica basicHttpBinding y hace referencia a una configuración de enlace denominada `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="69d85-142">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="69d85-143">El certificado que el servicio utiliza para autenticarse al cliente se establece en la sección `behaviors` del archivo de configuración bajo el elemento `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="69d85-143">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="69d85-144">El modo de la validación que se aplica al certificado que el cliente utiliza para autenticarse al servicio también se establece en la sección `behaviors` bajo el elemento `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="69d85-144">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="69d85-145">El mismo enlace y detalles de seguridad se especifican en el archivo de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="69d85-145">The same binding and security details are specified in the client configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="69d85-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="69d85-146">See also</span></span>

- [<span data-ttu-id="69d85-147">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="69d85-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="69d85-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="69d85-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="69d85-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="69d85-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="69d85-150">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="69d85-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
