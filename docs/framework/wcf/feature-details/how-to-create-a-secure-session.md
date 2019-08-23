---
title: Procedimiento para crear una sesión segura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
ms.openlocfilehash: bdb0f89b950d086e04cbb9d6da161bd315fc64b3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934380"
---
# <a name="how-to-create-a-secure-session"></a><span data-ttu-id="f80b9-102">Procedimiento para crear una sesión segura</span><span class="sxs-lookup"><span data-stu-id="f80b9-102">How to: Create a Secure Session</span></span>
<span data-ttu-id="f80b9-103">A excepción del enlace de [ \<> basicHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) , los enlaces proporcionados por el sistema en Windows Communication Foundation (WCF) usan automáticamente sesiones seguras cuando la seguridad de mensajes está habilitada.</span><span class="sxs-lookup"><span data-stu-id="f80b9-103">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, the system-provided bindings in Windows Communication Foundation (WCF) automatically use secure sessions when message security is enabled.</span></span>  
  
 <span data-ttu-id="f80b9-104">De forma predeterminada, las sesiones seguras no permanecen en ningún servidor reciclado.</span><span class="sxs-lookup"><span data-stu-id="f80b9-104">By default, secure sessions do not survive a Web server that is recycled.</span></span> <span data-ttu-id="f80b9-105">Cuando se establece una sesión segura, el cliente y el servicio almacenan en memoria caché la clave asociada a la sesión segura.</span><span class="sxs-lookup"><span data-stu-id="f80b9-105">When a secure session is established, the client and the service cache the key that is associated with the secure session.</span></span> <span data-ttu-id="f80b9-106">Cuando se intercambian los mensajes, se intercambia solo un identificador de la clave almacenada en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="f80b9-106">As the messages are exchanged, only an identifier to the cached key is exchanged.</span></span> <span data-ttu-id="f80b9-107">Si se recicla el servidor web, también se recicla la memoria en caché, de manera que el servidor web no puede recuperar la clave almacenada en memoria caché para el identificador.</span><span class="sxs-lookup"><span data-stu-id="f80b9-107">If the Web server is recycled, the cache is also recycled, such that the Web server cannot retrieve the cached key for the identifier.</span></span> <span data-ttu-id="f80b9-108">Si ocurre esto, se produce una excepción que se devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="f80b9-108">If this happens, an exception is thrown back to the client.</span></span> <span data-ttu-id="f80b9-109">Las sesiones seguras que usan un token de contexto de seguridad (SCT) con estado pueden sobrevivir en un servidor web que se recicle.</span><span class="sxs-lookup"><span data-stu-id="f80b9-109">Secure sessions that use a stateful security context token (SCT) can survive a Web server being recycled.</span></span> <span data-ttu-id="f80b9-110">Para obtener más información sobre el uso de un SCT con estado en una sesión [segura, consulte How to: Cree un token de contexto de seguridad para una](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)sesión segura.</span><span class="sxs-lookup"><span data-stu-id="f80b9-110">For more information about using a stateful SCT in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a><span data-ttu-id="f80b9-111">Para especificar que un servicio utiliza las sesiones seguras utilizando uno de los enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="f80b9-111">To specify that a service uses secure sessions by using one of the system-provided bindings</span></span>  
  
- <span data-ttu-id="f80b9-112">Configure un servicio para utilizar un enlace proporcionado por el sistema que admite seguridad de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f80b9-112">Configure a service to use a system-provided binding that supports message security.</span></span>  
  
     <span data-ttu-id="f80b9-113">A excepción del enlace de [ \<> basicHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) , cuando los enlaces proporcionados por el sistema se configuran para usar la seguridad de mensajes, WCF usa automáticamente sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="f80b9-113">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, when the system-provided bindings are configured to use message security, WCF automatically uses secure sessions.</span></span> <span data-ttu-id="f80b9-114">La siguiente tabla detalla los enlaces proporcionados por el sistema que admiten seguridad de mensaje y si la seguridad de mensaje es el mecanismo de seguridad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f80b9-114">The following table lists the system-provided bindings that support message security and whether message security is the default security mechanism.</span></span>  
  
    |<span data-ttu-id="f80b9-115">Enlace proporcionado por el sistema</span><span class="sxs-lookup"><span data-stu-id="f80b9-115">System-provided binding</span></span>|<span data-ttu-id="f80b9-116">Elemento de configuración</span><span class="sxs-lookup"><span data-stu-id="f80b9-116">Configuration element</span></span>|<span data-ttu-id="f80b9-117">Seguridad de mensaje activada de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="f80b9-117">Message security on by default</span></span>|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[<span data-ttu-id="f80b9-118">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="f80b9-118">\<basicHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|<span data-ttu-id="f80b9-119">Sin</span><span class="sxs-lookup"><span data-stu-id="f80b9-119">No</span></span>|  
    |<xref:System.ServiceModel.WSHttpBinding>|[<span data-ttu-id="f80b9-120">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="f80b9-120">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="f80b9-121">Sí</span><span class="sxs-lookup"><span data-stu-id="f80b9-121">Yes</span></span>|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[<span data-ttu-id="f80b9-122">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="f80b9-122">\<wsDualHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|<span data-ttu-id="f80b9-123">Sí</span><span class="sxs-lookup"><span data-stu-id="f80b9-123">Yes</span></span>|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[<span data-ttu-id="f80b9-124">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="f80b9-124">\<wsFederationHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|<span data-ttu-id="f80b9-125">Sí</span><span class="sxs-lookup"><span data-stu-id="f80b9-125">Yes</span></span>|  
    |<xref:System.ServiceModel.NetTcpBinding>|[<span data-ttu-id="f80b9-126">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="f80b9-126">\<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|<span data-ttu-id="f80b9-127">Sin</span><span class="sxs-lookup"><span data-stu-id="f80b9-127">No</span></span>|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[<span data-ttu-id="f80b9-128">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="f80b9-128">\<netMsmqBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|<span data-ttu-id="f80b9-129">Sin</span><span class="sxs-lookup"><span data-stu-id="f80b9-129">No</span></span>|  
  
     <span data-ttu-id="f80b9-130">En el ejemplo de código siguiente se usa la `wsHttpBinding_Calculator` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)configuración para especificar un enlace denominado que usa wsHttpBinding >, seguridad de mensajes y sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="f80b9-130">The following code example uses configuration to specify a binding named `wsHttpBinding_Calculator` that uses the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions.</span></span>  
  
    ```xml  
    <bindings>  
      <WSHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </WSHttpBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="f80b9-131">En el ejemplo de código siguiente se especifica que se utiliza [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), la seguridad de mensajes y las sesiones `secureCalculator` seguras para proteger el servicio.</span><span class="sxs-lookup"><span data-stu-id="f80b9-131">The following code example specifies that the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions are used to secure the `secureCalculator` service.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    > <span data-ttu-id="f80b9-132">Las sesiones seguras pueden desactivarse para el [ \<> wsHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) estableciendo el `establishSecurityContext` atributo en `false`.</span><span class="sxs-lookup"><span data-stu-id="f80b9-132">Secure sessions can be turned off for the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) by setting the `establishSecurityContext` attribute to `false`.</span></span> <span data-ttu-id="f80b9-133">Para los otros enlaces proporcionados por el sistema, las sesiones seguras pueden desactivarse solo mediante la creación un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="f80b9-133">For the other system-provided bindings, secure sessions can only be turned off by creating a custom binding.</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a><span data-ttu-id="f80b9-134">Especificar que un servicio utiliza sesiones seguras utilizando un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="f80b9-134">To specify that a service uses secure sessions by using a custom binding</span></span>  
  
- <span data-ttu-id="f80b9-135">Cree un enlace personalizado que especifica que una sesión segura protege los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="f80b9-135">Create a custom binding that specifies that SOAP messages are protected by a secure session.</span></span>  
  
     <span data-ttu-id="f80b9-136">Para obtener más información acerca de cómo crear un enlace [personalizado, consulte Cómo: Personalizar un enlace](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)proporcionado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="f80b9-136">For more information about creating a custom binding, see [How to: Customize a System-Provided Binding](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
     <span data-ttu-id="f80b9-137">El ejemplo de código siguiente utiliza la configuración para especificar un enlace personalizado que envía mensajes utilizando una sesión segura.</span><span class="sxs-lookup"><span data-stu-id="f80b9-137">The following code example uses configuration to specify a custom binding that messages using a secure session.</span></span>  
  
    ```xml  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="customBinding_Calculator">  
          <security authenticationMode="SecureConversation" />  
          <secureConversationBootstrap authenticationMode="SspiNegotiated" />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="f80b9-138">El ejemplo de código siguiente crea un enlace personalizado que utiliza el modo de autenticación <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> para arrancar una sesión segura.</span><span class="sxs-lookup"><span data-stu-id="f80b9-138">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f80b9-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="f80b9-139">See also</span></span>

- [<span data-ttu-id="f80b9-140">Información general sobre enlaces WCF</span><span class="sxs-lookup"><span data-stu-id="f80b9-140">WCF Bindings Overview</span></span>](../../../../docs/framework/wcf/bindings-overview.md)
