---
title: Filtrar Crear una sesión segura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
ms.openlocfilehash: d484bb6d11e7e81ebd14586450f16d8a18bcaa54
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "58463636"
---
# <a name="how-to-create-a-secure-session"></a><span data-ttu-id="1895c-102">Filtrar Crear una sesión segura</span><span class="sxs-lookup"><span data-stu-id="1895c-102">How to: Create a Secure Session</span></span>
<span data-ttu-id="1895c-103">Con la excepción de la [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) enlace, los enlaces proporcionados por el sistema en Windows Communication Foundation (WCF) utilizan automáticamente sesiones seguras cuando está habilitada la seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="1895c-103">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, the system-provided bindings in Windows Communication Foundation (WCF) automatically use secure sessions when message security is enabled.</span></span>  
  
 <span data-ttu-id="1895c-104">De forma predeterminada, las sesiones seguras no permanecen en ningún servidor reciclado.</span><span class="sxs-lookup"><span data-stu-id="1895c-104">By default, secure sessions do not survive a Web server that is recycled.</span></span> <span data-ttu-id="1895c-105">Cuando se establece una sesión segura, el cliente y el servicio almacenan en memoria caché la clave asociada a la sesión segura.</span><span class="sxs-lookup"><span data-stu-id="1895c-105">When a secure session is established, the client and the service cache the key that is associated with the secure session.</span></span> <span data-ttu-id="1895c-106">Cuando se intercambian los mensajes, se intercambia solo un identificador de la clave almacenada en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="1895c-106">As the messages are exchanged, only an identifier to the cached key is exchanged.</span></span> <span data-ttu-id="1895c-107">Si se recicla el servidor web, también se recicla la memoria en caché, de manera que el servidor web no puede recuperar la clave almacenada en memoria caché para el identificador.</span><span class="sxs-lookup"><span data-stu-id="1895c-107">If the Web server is recycled, the cache is also recycled, such that the Web server cannot retrieve the cached key for the identifier.</span></span> <span data-ttu-id="1895c-108">Si ocurre esto, se produce una excepción que se devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="1895c-108">If this happens, an exception is thrown back to the client.</span></span> <span data-ttu-id="1895c-109">Las sesiones seguras que usan un token de contexto de seguridad (SCT) con estado pueden sobrevivir en un servidor web que se recicle.</span><span class="sxs-lookup"><span data-stu-id="1895c-109">Secure sessions that use a stateful security context token (SCT) can survive a Web server being recycled.</span></span> <span data-ttu-id="1895c-110">Para obtener más información acerca de cómo utilizar un SCT con estado en una sesión segura, consulte [Cómo: Crear un contexto de seguridad para una sesión segura Token](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span><span class="sxs-lookup"><span data-stu-id="1895c-110">For more information about using a stateful SCT in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a><span data-ttu-id="1895c-111">Para especificar que un servicio utiliza las sesiones seguras utilizando uno de los enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="1895c-111">To specify that a service uses secure sessions by using one of the system-provided bindings</span></span>  
  
-   <span data-ttu-id="1895c-112">Configure un servicio para utilizar un enlace proporcionado por el sistema que admite seguridad de mensaje.</span><span class="sxs-lookup"><span data-stu-id="1895c-112">Configure a service to use a system-provided binding that supports message security.</span></span>  
  
     <span data-ttu-id="1895c-113">Con la excepción de la [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) enlace, cuando se configuran los enlaces proporcionados por el sistema para usar automáticamente la seguridad de mensajes, WCF utiliza las sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="1895c-113">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, when the system-provided bindings are configured to use message security, WCF automatically uses secure sessions.</span></span> <span data-ttu-id="1895c-114">La siguiente tabla detalla los enlaces proporcionados por el sistema que admiten seguridad de mensaje y si la seguridad de mensaje es el mecanismo de seguridad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1895c-114">The following table lists the system-provided bindings that support message security and whether message security is the default security mechanism.</span></span>  
  
    |<span data-ttu-id="1895c-115">Enlace proporcionado por el sistema</span><span class="sxs-lookup"><span data-stu-id="1895c-115">System-provided binding</span></span>|<span data-ttu-id="1895c-116">Elemento de configuración </span><span class="sxs-lookup"><span data-stu-id="1895c-116">Configuration element</span></span>|<span data-ttu-id="1895c-117">Seguridad de mensaje activada de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="1895c-117">Message security on by default</span></span>|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[<span data-ttu-id="1895c-118">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1895c-118">\<basicHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|<span data-ttu-id="1895c-119">No</span><span class="sxs-lookup"><span data-stu-id="1895c-119">No</span></span>|  
    |<xref:System.ServiceModel.WSHttpBinding>|[<span data-ttu-id="1895c-120">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1895c-120">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="1895c-121">Sí</span><span class="sxs-lookup"><span data-stu-id="1895c-121">Yes</span></span>|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[<span data-ttu-id="1895c-122">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1895c-122">\<wsDualHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|<span data-ttu-id="1895c-123">Sí</span><span class="sxs-lookup"><span data-stu-id="1895c-123">Yes</span></span>|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[<span data-ttu-id="1895c-124">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1895c-124">\<wsFederationHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|<span data-ttu-id="1895c-125">Sí</span><span class="sxs-lookup"><span data-stu-id="1895c-125">Yes</span></span>|  
    |<xref:System.ServiceModel.NetTcpBinding>|[<span data-ttu-id="1895c-126">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="1895c-126">\<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|<span data-ttu-id="1895c-127">No</span><span class="sxs-lookup"><span data-stu-id="1895c-127">No</span></span>|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[<span data-ttu-id="1895c-128">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="1895c-128">\<netMsmqBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|<span data-ttu-id="1895c-129">No</span><span class="sxs-lookup"><span data-stu-id="1895c-129">No</span></span>|  
  
     <span data-ttu-id="1895c-130">En el ejemplo de código siguiente se usa la configuración para especificar un enlace denominado `wsHttpBinding_Calculator` que usa el [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), seguridad de mensajes y protección de las sesiones.</span><span class="sxs-lookup"><span data-stu-id="1895c-130">The following code example uses configuration to specify a binding named `wsHttpBinding_Calculator` that uses the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions.</span></span>  
  
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
  
     <span data-ttu-id="1895c-131">El ejemplo de código siguiente especifica que el [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), seguridad de mensajes y protección de las sesiones se utilizan para proteger el `secureCalculator` service.</span><span class="sxs-lookup"><span data-stu-id="1895c-131">The following code example specifies that the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions are used to secure the `secureCalculator` service.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="1895c-132">Las sesiones seguras pueden desactivarse para el [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) estableciendo el `establishSecurityContext` atributo `false`.</span><span class="sxs-lookup"><span data-stu-id="1895c-132">Secure sessions can be turned off for the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) by setting the `establishSecurityContext` attribute to `false`.</span></span> <span data-ttu-id="1895c-133">Para los otros enlaces proporcionados por el sistema, las sesiones seguras pueden desactivarse solo mediante la creación un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="1895c-133">For the other system-provided bindings, secure sessions can only be turned off by creating a custom binding.</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a><span data-ttu-id="1895c-134">Especificar que un servicio utiliza sesiones seguras utilizando un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="1895c-134">To specify that a service uses secure sessions by using a custom binding</span></span>  
  
-   <span data-ttu-id="1895c-135">Cree un enlace personalizado que especifica que una sesión segura protege los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="1895c-135">Create a custom binding that specifies that SOAP messages are protected by a secure session.</span></span>  
  
     <span data-ttu-id="1895c-136">Para obtener más información acerca de cómo crear un enlace personalizado, vea [Cómo: Personalización de un enlace proporcionado por el sistema](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="1895c-136">For more information about creating a custom binding, see [How to: Customize a System-Provided Binding](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
     <span data-ttu-id="1895c-137">El ejemplo de código siguiente utiliza la configuración para especificar un enlace personalizado que envía mensajes utilizando una sesión segura.</span><span class="sxs-lookup"><span data-stu-id="1895c-137">The following code example uses configuration to specify a custom binding that messages using a secure session.</span></span>  
  
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
  
     <span data-ttu-id="1895c-138">El ejemplo de código siguiente crea un enlace personalizado que utiliza el modo de autenticación <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> para arrancar una sesión segura.</span><span class="sxs-lookup"><span data-stu-id="1895c-138">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1895c-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="1895c-139">See also</span></span>
- [<span data-ttu-id="1895c-140">Información general sobre enlaces WCF</span><span class="sxs-lookup"><span data-stu-id="1895c-140">WCF Bindings Overview</span></span>](../../../../docs/framework/wcf/bindings-overview.md)
