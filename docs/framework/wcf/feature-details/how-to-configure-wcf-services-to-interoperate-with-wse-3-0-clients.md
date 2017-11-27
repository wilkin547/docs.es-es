---
title: "Cómo: Configurar los servicios WCF para interoperar con clientes de WSE 3.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 099fb059e375e0e76cffb5389191011d866b2d8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="8d8c6-102">Cómo: Configurar los servicios WCF para interoperar con clientes de WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="8d8c6-102">How to: Configure WCF Services to Interoperate with WSE 3.0 Clients</span></span>
<span data-ttu-id="8d8c6-103">Los servicios de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] son compatibles en el nivel de conexión con Web Services Enhancements 3.0 para clientes de Microsoft .NET (WSE) cuando los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se configuran para utilizar la versión de agosto de 2004 de la especificación WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) clients when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="8d8c6-104">Para permitir a un servicio de WCF interoperar con clientes de WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="8d8c6-104">To enable a WCF service to interoperate with WSE 3.0 clients</span></span>  
  
1.  <span data-ttu-id="8d8c6-105">Defina un enlace personalizado para el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d8c6-105">Define a custom binding for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
     <span data-ttu-id="8d8c6-106">Para especificar que la versión de agosto de 2004 de la especificación WS-Addressing se utiliza para la codificación de mensajes, se deberá crear un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-106">To specify that the August 2004 version of the WS-Addressing specification is used for message encoding, a custom binding must be created.</span></span>  
  
    1.  <span data-ttu-id="8d8c6-107">Agregar un elemento secundario [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) a la [ \<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-107">Add a child [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) of the service's configuration file.</span></span>  
  
    2.  <span data-ttu-id="8d8c6-108">Especifique un nombre para el enlace agregando un [ \<enlace >](../../../../docs/framework/misc/binding.md) a la [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) y estableciendo el `name` atributo.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-108">Specify a name for the binding, by adding a [\<binding>](../../../../docs/framework/misc/binding.md) to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) and setting the `name` attribute.</span></span>  
  
    3.  <span data-ttu-id="8d8c6-109">Especifique un modo de autenticación y la versión de las especificaciones de WS-Security que se utilizan para proteger los mensajes que son compatibles con WSE 3.0, mediante la adición de un elemento secundario [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) a la [ \<enlace >](../../../../docs/framework/misc/binding.md).</span><span class="sxs-lookup"><span data-stu-id="8d8c6-109">Specify an authentication mode and the version of the WS-Security specifications that are used to secure messages that are compatible with WSE 3.0, by adding a child [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) to the [\<binding>](../../../../docs/framework/misc/binding.md).</span></span>  
  
         <span data-ttu-id="8d8c6-110">Para establecer el modo de autenticación, establezca el `authenicationMode` atributo de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="8d8c6-110">To set the authentication mode, set the `authenicationMode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="8d8c6-111">Un modo de autenticación es aproximadamente el equivalente a una aserción de seguridad lista para ser usada en WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-111">An authentication mode is roughly equivalent to a turnkey security assertion in WSE 3.0.</span></span> <span data-ttu-id="8d8c6-112">La tabla siguiente asigna los modos de autenticación en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a las aserciones de seguridad listas para ser usadas en WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-112">The following table maps authentication modes in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to turnkey security assertions in WSE 3.0.</span></span>  
  
        |<span data-ttu-id="8d8c6-113">Modo de autenticación WCF</span><span class="sxs-lookup"><span data-stu-id="8d8c6-113">WCF Authentication Mode</span></span>|<span data-ttu-id="8d8c6-114">Aserción de seguridad lista para ser usada de WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="8d8c6-114">WSE 3.0 turnkey security assertion</span></span>|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         <span data-ttu-id="8d8c6-115">\*Una de las diferencias principales entre el `mutualCertificate10Security` y `mutualCertificate11Security` aserciones de seguridad inmediata es la versión de la especificación de WS-Security que WSE utiliza para proteger los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-115">\* One of the primary differences between the `mutualCertificate10Security` and `mutualCertificate11Security` turnkey security assertions is the version of the WS-Security specification that WSE uses to secure the SOAP messages.</span></span> <span data-ttu-id="8d8c6-116">Para `mutualCertificate10Security`, se utiliza WS-Security 1.0, mientras que WS-Security 1.1 se usa para `mutualCertificate11Security`.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-116">For `mutualCertificate10Security`, WS-Security 1.0 is used, whereas WS-Security 1.1 is used for `mutualCertificate11Security`.</span></span> <span data-ttu-id="8d8c6-117">Para [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], se especifica la versión de la especificación WS-Security en el `messageSecurityVersion` atributo de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="8d8c6-117">For [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], the version of the WS-Security specification is specified in the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="8d8c6-118">Para establecer la versión de la especificación de WS-Security que se usa para proteger los mensajes SOAP, establezca la `messageSecurityVersion` atributo de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="8d8c6-118">To set the version of the WS-Security specification that is used to secure SOAP messages, set the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="8d8c6-119">Para interoperar con WSE 3.0, defina el valor del atributo `messageSecurityVersion` en <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-119">To interoperate with WSE 3.0, set the value of the `messageSecurityVersion` attribute to <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span></span>  
  
    4.  <span data-ttu-id="8d8c6-120">Especificar que se utilice la versión de agosto de 2004 de la especificación de WS-Addressing [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] agregando un [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) y establezca el `messageVersion` a su valor a <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-120">Specify that the August 2004 version of the WS-Addressing specification is used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by adding a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) and set the `messageVersion` to its value to <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="8d8c6-121">Cuando utilice SOAP 1.2, establezca el atributo `messageVersion` en <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-121">When you are using SOAP 1.2, set the `messageVersion` attribute to <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span></span>  
  
2.  <span data-ttu-id="8d8c6-122">Especifique que el servicio utiliza el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-122">Specify that the service uses the custom binding.</span></span>  
  
    1.  <span data-ttu-id="8d8c6-123">Establecer el `binding` atributo de la [ \<extremo >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento `customBinding`.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-123">Set the `binding` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to `customBinding`.</span></span>  
  
    2.  <span data-ttu-id="8d8c6-124">Establecer el `bindingConfiguration` atributo de la [ \<extremo >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) en el valor especificado en el `name` atributo de la [ \<enlace >](../../../../docs/framework/misc/binding.md) personalizada de enlace.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-124">Set the `bindingConfiguration` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to the value specified in the `name` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) for the custom binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d8c6-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d8c6-125">Example</span></span>  
 <span data-ttu-id="8d8c6-126">El ejemplo de código siguiente especifica que `Service.HelloWorldService` utiliza un enlace personalizado para interoperar con clientes de WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-126">The following code example specifies that the `Service.HelloWorldService` uses a custom binding to interoperate with WSE 3.0 clients.</span></span> <span data-ttu-id="8d8c6-127">El enlace personalizado especifica que se utiliza la versión de agosto de 2004 del conjunto de especificaciones WS-Addressing y WS-Security 1.1 para codificar los mensajes intercambiados.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-127">The custom binding specifies that the August 2004 version of the WS-Addressing and the WS-Security 1.1 set of specifications are used to encode the exchanged messages.</span></span> <span data-ttu-id="8d8c6-128">Los mensajes se protegen utilizando el modo de autenticación <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>.</span><span class="sxs-lookup"><span data-stu-id="8d8c6-128">The messages are secured using the <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> authentication mode.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
        behaviorConfiguration="ServiceBehavior"   
        name="Service.HelloWorldService">  
        <endpoint binding="customBinding" address=""  
          bindingConfiguration="ServiceBinding"  
          contract="Service.IHelloWorld"></endpoint>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="ServiceBinding">  
          <security authenticationMode="AnonymousForCertificate"  
                  messageProtectionOrder="SignBeforeEncrypt"  
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"  
                  requireDerivedKeys="false">  
          </security>  
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">  
        <serviceCredentials>  
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>  
        </serviceCredentials>  
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d8c6-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d8c6-129">See Also</span></span>  
 [<span data-ttu-id="8d8c6-130">Cómo: personalizar un enlace proporcionado por el sistema</span><span class="sxs-lookup"><span data-stu-id="8d8c6-130">How to: Customize a System-Provided Binding</span></span>](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
