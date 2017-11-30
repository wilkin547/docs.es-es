---
title: "Cómo: Crear una sesión segura"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: f2393209352f18eb25b9837ca1ad8ca2746b91d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-secure-session"></a><span data-ttu-id="04dda-102">Cómo: Crear una sesión segura</span><span class="sxs-lookup"><span data-stu-id="04dda-102">How to: Create a Secure Session</span></span>
<span data-ttu-id="04dda-103">Con la excepción de la [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) el enlace, los enlaces proporcionados por el sistema de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utilizar automáticamente las sesiones seguras cuando está habilitada la seguridad de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="04dda-103">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, the system-provided bindings in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] automatically use secure sessions when message security is enabled.</span></span>  
  
 <span data-ttu-id="04dda-104">De forma predeterminada, las sesiones seguras no permanecen en ningún servidor reciclado.</span><span class="sxs-lookup"><span data-stu-id="04dda-104">By default, secure sessions do not survive a Web server that is recycled.</span></span> <span data-ttu-id="04dda-105">Cuando se establece una sesión segura, el cliente y el servicio almacenan en memoria caché la clave asociada a la sesión segura.</span><span class="sxs-lookup"><span data-stu-id="04dda-105">When a secure session is established, the client and the service cache the key that is associated with the secure session.</span></span> <span data-ttu-id="04dda-106">Cuando se intercambian los mensajes, se intercambia solo un identificador de la clave almacenada en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="04dda-106">As the messages are exchanged, only an identifier to the cached key is exchanged.</span></span> <span data-ttu-id="04dda-107">Si se recicla el servidor web, también se recicla la memoria en caché, de manera que el servidor web no puede recuperar la clave almacenada en memoria caché para el identificador.</span><span class="sxs-lookup"><span data-stu-id="04dda-107">If the Web server is recycled, the cache is also recycled, such that the Web server cannot retrieve the cached key for the identifier.</span></span> <span data-ttu-id="04dda-108">Si ocurre esto, se produce una excepción que se devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="04dda-108">If this happens, an exception is thrown back to the client.</span></span> <span data-ttu-id="04dda-109">Las sesiones seguras que usan un token de contexto de seguridad (SCT) con estado pueden sobrevivir en un servidor web que se recicle.</span><span class="sxs-lookup"><span data-stu-id="04dda-109">Secure sessions that use a stateful security context token (SCT) can survive a Web server being recycled.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="04dda-110">uso de un SCT con estado en una sesión segura, consulte [Cómo: crear un Token de contexto de seguridad para una sesión segura](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span><span class="sxs-lookup"><span data-stu-id="04dda-110"> using a stateful SCT in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a><span data-ttu-id="04dda-111">Para especificar que un servicio utiliza las sesiones seguras utilizando uno de los enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="04dda-111">To specify that a service uses secure sessions by using one of the system-provided bindings</span></span>  
  
-   <span data-ttu-id="04dda-112">Configure un servicio para utilizar un enlace proporcionado por el sistema que admite seguridad de mensaje.</span><span class="sxs-lookup"><span data-stu-id="04dda-112">Configure a service to use a system-provided binding that supports message security.</span></span>  
  
     <span data-ttu-id="04dda-113">Con la excepción de la [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) enlace, cuando los enlaces proporcionados por el sistema se configuran para utilizar la seguridad de mensaje, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa automáticamente las sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="04dda-113">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, when the system-provided bindings are configured to use message security, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatically uses secure sessions.</span></span> <span data-ttu-id="04dda-114">La siguiente tabla detalla los enlaces proporcionados por el sistema que admiten seguridad de mensaje y si la seguridad de mensaje es el mecanismo de seguridad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="04dda-114">The following table lists the system-provided bindings that support message security and whether message security is the default security mechanism.</span></span>  
  
    |<span data-ttu-id="04dda-115">Enlace proporcionado por el sistema</span><span class="sxs-lookup"><span data-stu-id="04dda-115">System-provided binding</span></span>|<span data-ttu-id="04dda-116">Elemento de configuración </span><span class="sxs-lookup"><span data-stu-id="04dda-116">Configuration element</span></span>|<span data-ttu-id="04dda-117">Seguridad de mensaje activada de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="04dda-117">Message security on by default</span></span>|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[<span data-ttu-id="04dda-118">\<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="04dda-118">\<basicHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|<span data-ttu-id="04dda-119">No</span><span class="sxs-lookup"><span data-stu-id="04dda-119">No</span></span>|  
    |<xref:System.ServiceModel.WSHttpBinding>|[<span data-ttu-id="04dda-120">\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="04dda-120">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="04dda-121">Sí</span><span class="sxs-lookup"><span data-stu-id="04dda-121">Yes</span></span>|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[<span data-ttu-id="04dda-122">\<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="04dda-122">\<wsDualHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|<span data-ttu-id="04dda-123">Sí</span><span class="sxs-lookup"><span data-stu-id="04dda-123">Yes</span></span>|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[<span data-ttu-id="04dda-124">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="04dda-124">\<wsFederationHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|<span data-ttu-id="04dda-125">Sí</span><span class="sxs-lookup"><span data-stu-id="04dda-125">Yes</span></span>|  
    |<xref:System.ServiceModel.NetTcpBinding>|[<span data-ttu-id="04dda-126">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="04dda-126">\<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|<span data-ttu-id="04dda-127">No</span><span class="sxs-lookup"><span data-stu-id="04dda-127">No</span></span>|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[<span data-ttu-id="04dda-128">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="04dda-128">\<netMsmqBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|<span data-ttu-id="04dda-129">No</span><span class="sxs-lookup"><span data-stu-id="04dda-129">No</span></span>|  
  
     <span data-ttu-id="04dda-130">En el ejemplo de código siguiente se utiliza la configuración para especificar un enlace denominado `wsHttpBinding_Calculator` que usa el [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), seguridad de mensajes y proteger las sesiones.</span><span class="sxs-lookup"><span data-stu-id="04dda-130">The following code example uses configuration to specify a binding named `wsHttpBinding_Calculator` that uses the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions.</span></span>  
  
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
  
     <span data-ttu-id="04dda-131">En el ejemplo de código siguiente se especifica que la [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), seguridad de mensajes y proteger las sesiones se utilizan para proteger el `secureCalculator` service.</span><span class="sxs-lookup"><span data-stu-id="04dda-131">The following code example specifies that the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions are used to secure the `secureCalculator` service.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="04dda-132">Las sesiones seguras pueden desactivarse para la [ <wsHttpBinding> ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) estableciendo la `establishSecurityContext` atribuir a `false`.</span><span class="sxs-lookup"><span data-stu-id="04dda-132">Secure sessions can be turned off for the [<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) by setting the `establishSecurityContext` attribute to `false`.</span></span> <span data-ttu-id="04dda-133">Para los otros enlaces proporcionados por el sistema, las sesiones seguras pueden desactivarse solo mediante la creación un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="04dda-133">For the other system-provided bindings, secure sessions can only be turned off by creating a custom binding.</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a><span data-ttu-id="04dda-134">Especificar que un servicio utiliza sesiones seguras utilizando un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="04dda-134">To specify that a service uses secure sessions by using a custom binding</span></span>  
  
-   <span data-ttu-id="04dda-135">Cree un enlace personalizado que especifica que una sesión segura protege los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="04dda-135">Create a custom binding that specifies that SOAP messages are protected by a secure session.</span></span>  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="04dda-136">crear un enlace personalizado, vea [Cómo: personalizar un enlace proporcionados](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="04dda-136"> creating a custom binding, see [How to: Customize a System-Provided Binding](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
     <span data-ttu-id="04dda-137">El ejemplo de código siguiente utiliza la configuración para especificar un enlace personalizado que envía mensajes utilizando una sesión segura.</span><span class="sxs-lookup"><span data-stu-id="04dda-137">The following code example uses configuration to specify a custom binding that messages using a secure session.</span></span>  
  
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
  
     <span data-ttu-id="04dda-138">El ejemplo de código siguiente crea un enlace personalizado que utiliza el modo de autenticación <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> para arrancar una sesión segura.</span><span class="sxs-lookup"><span data-stu-id="04dda-138">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="04dda-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="04dda-139">See Also</span></span>  
 [<span data-ttu-id="04dda-140">Información general sobre enlaces WCF</span><span class="sxs-lookup"><span data-stu-id="04dda-140">WCF Bindings Overview</span></span>](../../../../docs/framework/wcf/bindings-overview.md)
