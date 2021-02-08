---
description: Más información acerca de cómo configurar servicios WCF para interoperar con clientes de WSE 3,0
title: Procedimiento para configurar los servicios WCF para interoperar con clientes de WSE 3.0
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: d48b24ac7787a9863744ee9b6a4a984cb6b371e4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779938"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="b0890-103">Procedimiento para configurar los servicios WCF para interoperar con clientes de WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="b0890-103">How to: Configure WCF Services to Interoperate with WSE 3.0 Clients</span></span>

<span data-ttu-id="b0890-104">Los servicios de Windows Communication Foundation (WCF) son compatibles en el nivel de conexión con las mejoras de servicios web 3,0 para los clientes de Microsoft .NET (WSE) cuando los servicios WCF están configurados para usar la versión 2004 de agosto de la especificación WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="b0890-104">Windows Communication Foundation (WCF) services are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) clients when WCF services are configured to use the August 2004 version of the WS-Addressing specification.</span></span>

### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="b0890-105">Para permitir a un servicio de WCF interoperar con clientes de WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="b0890-105">To enable a WCF service to interoperate with WSE 3.0 clients</span></span>

1. <span data-ttu-id="b0890-106">Defina un enlace personalizado para el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="b0890-106">Define a custom binding for the WCF service.</span></span>

    <span data-ttu-id="b0890-107">Para especificar que la versión de agosto de 2004 de la especificación WS-Addressing se utiliza para la codificación de mensajes, se deberá crear un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="b0890-107">To specify that the August 2004 version of the WS-Addressing specification is used for message encoding, a custom binding must be created.</span></span>

    1. <span data-ttu-id="b0890-108">Agregue un elemento secundario [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) al [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) del archivo de configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="b0890-108">Add a child [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) to the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) of the service's configuration file.</span></span>

    2. <span data-ttu-id="b0890-109">Especifique un nombre para el enlace agregando [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) y estableciendo el `name` atributo.</span><span class="sxs-lookup"><span data-stu-id="b0890-109">Specify a name for the binding, by adding a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) to the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) and setting the `name` attribute.</span></span>

    3. <span data-ttu-id="b0890-110">Especifique un modo de autenticación y la versión de las especificaciones de WS-Security que se usan para proteger los mensajes que son compatibles con WSE 3,0, agregando un elemento secundario [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) al [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) .</span><span class="sxs-lookup"><span data-stu-id="b0890-110">Specify an authentication mode and the version of the WS-Security specifications that are used to secure messages that are compatible with WSE 3.0, by adding a child [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) to the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md).</span></span>

        <span data-ttu-id="b0890-111">Para establecer el modo de autenticación, establezca el `authenticationMode` atributo de [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b0890-111">To set the authentication mode, set the `authenticationMode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="b0890-112">Un modo de autenticación es aproximadamente el equivalente a una aserción de seguridad lista para ser usada en WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="b0890-112">An authentication mode is roughly equivalent to a turnkey security assertion in WSE 3.0.</span></span> <span data-ttu-id="b0890-113">En la tabla siguiente se asignan modos de autenticación en WCF a las aserciones de seguridad llave en mano en WSE 3,0.</span><span class="sxs-lookup"><span data-stu-id="b0890-113">The following table maps authentication modes in WCF to turnkey security assertions in WSE 3.0.</span></span>

        |<span data-ttu-id="b0890-114">Modo de autenticación WCF</span><span class="sxs-lookup"><span data-stu-id="b0890-114">WCF Authentication Mode</span></span>|<span data-ttu-id="b0890-115">Aserción de seguridad lista para ser usada de WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="b0890-115">WSE 3.0 turnkey security assertion</span></span>|
        |-----------------------------|----------------------------------------|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|

        <span data-ttu-id="b0890-116">\* Una de las principales diferencias entre las `mutualCertificate10Security` `mutualCertificate11Security` aserciones de seguridad y llave en mano es la versión de la especificación WS-Security que WSE utiliza para proteger los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="b0890-116">\* One of the primary differences between the `mutualCertificate10Security` and `mutualCertificate11Security` turnkey security assertions is the version of the WS-Security specification that WSE uses to secure the SOAP messages.</span></span> <span data-ttu-id="b0890-117">Para `mutualCertificate10Security`, se utiliza WS-Security 1.0, mientras que WS-Security 1.1 se usa para `mutualCertificate11Security`.</span><span class="sxs-lookup"><span data-stu-id="b0890-117">For `mutualCertificate10Security`, WS-Security 1.0 is used, whereas WS-Security 1.1 is used for `mutualCertificate11Security`.</span></span> <span data-ttu-id="b0890-118">Para WCF, la versión de la especificación WS-Security se especifica en el `messageSecurityVersion` atributo de [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b0890-118">For WCF, the version of the WS-Security specification is specified in the `messageSecurityVersion` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>

        <span data-ttu-id="b0890-119">Para establecer la versión de la especificación WS-Security que se usa para proteger los mensajes SOAP, establezca el `messageSecurityVersion` atributo de [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b0890-119">To set the version of the WS-Security specification that is used to secure SOAP messages, set the `messageSecurityVersion` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="b0890-120">Para interoperar con WSE 3.0, defina el valor del atributo `messageSecurityVersion` en <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span><span class="sxs-lookup"><span data-stu-id="b0890-120">To interoperate with WSE 3.0, set the value of the `messageSecurityVersion` attribute to <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span></span>

    4. <span data-ttu-id="b0890-121">Especifique que WCF usa la versión de agosto de 2004 de la especificación WS-Addressing agregando [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) y establezca `messageVersion` en su valor en <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A> .</span><span class="sxs-lookup"><span data-stu-id="b0890-121">Specify that the August 2004 version of the WS-Addressing specification is used by WCF by adding a [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) and set the `messageVersion` to its value to <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b0890-122">Cuando utilice SOAP 1.2, establezca el atributo `messageVersion` en <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span><span class="sxs-lookup"><span data-stu-id="b0890-122">When you are using SOAP 1.2, set the `messageVersion` attribute to <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span></span>

2. <span data-ttu-id="b0890-123">Especifique que el servicio utiliza el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="b0890-123">Specify that the service uses the custom binding.</span></span>

    1. <span data-ttu-id="b0890-124">Establezca el `binding` atributo del [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) elemento en `customBinding` .</span><span class="sxs-lookup"><span data-stu-id="b0890-124">Set the `binding` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element to `customBinding`.</span></span>

    2. <span data-ttu-id="b0890-125">Establezca el `bindingConfiguration` atributo del [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) elemento en el valor especificado en el `name` atributo de [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="b0890-125">Set the `bindingConfiguration` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element to the value specified in the `name` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) for the custom binding.</span></span>

## <a name="example"></a><span data-ttu-id="b0890-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0890-126">Example</span></span>

<span data-ttu-id="b0890-127">El ejemplo de código siguiente especifica que `Service.HelloWorldService` utiliza un enlace personalizado para interoperar con clientes de WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="b0890-127">The following code example specifies that the `Service.HelloWorldService` uses a custom binding to interoperate with WSE 3.0 clients.</span></span> <span data-ttu-id="b0890-128">El enlace personalizado especifica que se utiliza la versión de agosto de 2004 del conjunto de especificaciones WS-Addressing y WS-Security 1.1 para codificar los mensajes intercambiados.</span><span class="sxs-lookup"><span data-stu-id="b0890-128">The custom binding specifies that the August 2004 version of the WS-Addressing and the WS-Security 1.1 set of specifications are used to encode the exchanged messages.</span></span> <span data-ttu-id="b0890-129">Los mensajes se protegen utilizando el modo de autenticación <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>.</span><span class="sxs-lookup"><span data-stu-id="b0890-129">The messages are secured using the <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> authentication mode.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b0890-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0890-130">See also</span></span>

- [<span data-ttu-id="b0890-131">Procedimiento para personalizar un enlace proporcionado por el sistema</span><span class="sxs-lookup"><span data-stu-id="b0890-131">How to: Customize a System-Provided Binding</span></span>](../extending/how-to-customize-a-system-provided-binding.md)
