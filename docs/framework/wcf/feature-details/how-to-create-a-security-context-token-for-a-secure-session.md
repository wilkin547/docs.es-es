---
title: Procedimiento para crear un token de contexto de seguridad para una sesión segura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
ms.openlocfilehash: 36cf5ce1aa6e0eef80123ac7008294062d7faf82
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598910"
---
# <a name="how-to-create-a-security-context-token-for-a-secure-session"></a><span data-ttu-id="2f813-102">Procedimiento para crear un token de contexto de seguridad para una sesión segura</span><span class="sxs-lookup"><span data-stu-id="2f813-102">How to: Create a Security Context Token for a Secure Session</span></span>
<span data-ttu-id="2f813-103">Mediante el uso de un token de contexto de seguridad con estado (SCT) en una sesión segura, la sesión puede soportar que el servicio se recicle.</span><span class="sxs-lookup"><span data-stu-id="2f813-103">By using a stateful security context token (SCT) in a secure session, the session can withstand the service being recycled.</span></span> <span data-ttu-id="2f813-104">Por ejemplo, cuando un SCT sin estado se utiliza en una sesión segura y se restablece Internet Information Services (IIS), a continuación, se pierden los datos de la sesión que están asociados al servicio.</span><span class="sxs-lookup"><span data-stu-id="2f813-104">For instance, when a stateless SCT is used in a secure session and Internet Information Services (IIS) is reset, then the session data that is associated with the service is lost.</span></span> <span data-ttu-id="2f813-105">Estos datos de la sesión incluyen una caché de token de SCT.</span><span class="sxs-lookup"><span data-stu-id="2f813-105">This session data includes an SCT token cache.</span></span> <span data-ttu-id="2f813-106">Así, la próxima vez que un cliente envíe un SCT sin estado al servicio, se devuelve un error, porque no se puede recuperar la clave que está asociada a SCT.</span><span class="sxs-lookup"><span data-stu-id="2f813-106">So, the next time a client sends the service a stateless SCT, an error is returned, because the key that is associated with the SCT cannot be retrieved.</span></span> <span data-ttu-id="2f813-107">Si, sin embargo, se utiliza un SCT con estado, la clave que está asociada a SCT se contiene dentro de SCT.</span><span class="sxs-lookup"><span data-stu-id="2f813-107">If, however, a stateful SCT is used, then the key that is associated with the SCT is contained within the SCT.</span></span> <span data-ttu-id="2f813-108">Dado que la clave se contiene dentro de SCT y, por tanto, dentro del mensaje, el reciclaje del servicio no afecta a la sesión segura.</span><span class="sxs-lookup"><span data-stu-id="2f813-108">Because the key is contained within the SCT and thus contained within the message, the secure session is not affected by the service being recycled.</span></span> <span data-ttu-id="2f813-109">De forma predeterminada, Windows Communication Foundation (WCF) usa SCT sin estado en una sesión segura.</span><span class="sxs-lookup"><span data-stu-id="2f813-109">By default, Windows Communication Foundation (WCF) uses stateless SCTs in a secure session.</span></span> <span data-ttu-id="2f813-110">En este tema se detalla cómo utilizar SCT con estado en una sesión segura.</span><span class="sxs-lookup"><span data-stu-id="2f813-110">This topic details how to use stateful SCTs in a secure session.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f813-111">Los SCT con estado no se puede utilizar en una sesión segura que implique un contrato que derive de <xref:System.ServiceModel.Channels.IDuplexChannel>.</span><span class="sxs-lookup"><span data-stu-id="2f813-111">Stateful SCTs cannot be used in a secure session that involves a contract that derives from <xref:System.ServiceModel.Channels.IDuplexChannel>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f813-112">Para las aplicaciones que utilizan SCT con estado en una sesión segura, la identidad del subproceso para el servicio debe ser una cuenta de usuario que tenga un perfil de usuario asociado.</span><span class="sxs-lookup"><span data-stu-id="2f813-112">For applications that use stateful SCTs in a secure session, the thread identity for the service must be a user account that has an associated user profile.</span></span> <span data-ttu-id="2f813-113">Cuando el servicio se ejecuta bajo una cuenta que no tiene un perfil de usuario, como `Local Service`, se puede producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="2f813-113">When the service is run under an account that does not have a user profile, such as `Local Service`, an exception may be thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f813-114">Cuando se requiere la suplantación en Windows XP, utilice una sesión segura sin un SCT con estado.</span><span class="sxs-lookup"><span data-stu-id="2f813-114">When impersonation is required on Windows XP, use a secure session without a stateful SCT.</span></span> <span data-ttu-id="2f813-115">Cuando se utilizan SCT con estado con suplantación, se produce una <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="2f813-115">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="2f813-116">Para obtener más información, vea [escenarios no admitidos](unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="2f813-116">For more information, see [Unsupported Scenarios](unsupported-scenarios.md).</span></span>  
  
### <a name="to-use-stateful-scts-in-a-secure-session"></a><span data-ttu-id="2f813-117">Para utilizar SCT con estado en una sesión segura</span><span class="sxs-lookup"><span data-stu-id="2f813-117">To use stateful SCTs in a secure session</span></span>  
  
- <span data-ttu-id="2f813-118">Cree un enlace personalizado que especifique que una sesión segura que utiliza un SCT con estado protege los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="2f813-118">Create a custom binding that specifies that SOAP messages are protected by a secure session that uses a stateful SCT.</span></span>  
  
    1. <span data-ttu-id="2f813-119">Defina un enlace personalizado, agregando [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) al archivo de configuración para el servicio.</span><span class="sxs-lookup"><span data-stu-id="2f813-119">Define a custom binding, by adding a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) to the configuration file for the service.</span></span>  
  
        ```xml  
        <customBinding>  
        </customBinding>
        ```  
  
    2. <span data-ttu-id="2f813-120">Agregue un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento secundario al [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="2f813-120">Add a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) child element to the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="2f813-121">Especifique un nombre de enlace estableciendo el atributo `name` en un nombre único dentro del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="2f813-121">Specify a binding name by setting the `name` attribute to a unique name within the configuration file.</span></span>  
  
        ```xml  
        <binding name="StatefulSCTSecureSession">  
        </binding>
        ```  
  
    3. <span data-ttu-id="2f813-122">Especifique el modo de autenticación para los mensajes enviados a y desde este servicio agregando un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento secundario al [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="2f813-122">Specify the authentication mode for messages sent to and from this service by adding a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) child element to the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="2f813-123">Especifique que se utiliza una sesión segura estableciendo el atributo `authenticationMode` en `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="2f813-123">Specify that a secure session is used by setting the `authenticationMode` attribute to `SecureConversation`.</span></span> <span data-ttu-id="2f813-124">Especifique que se utilizan SCT con estado estableciendo el atributo `requireSecurityContextCancellation` en `false`.</span><span class="sxs-lookup"><span data-stu-id="2f813-124">Specify that stateful SCTs are used by setting the `requireSecurityContextCancellation` attribute to `false`.</span></span>  
  
        ```xml  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">
        </security>
        ```  
  
    4. <span data-ttu-id="2f813-125">Especifique cómo se autentica el cliente mientras se establece la sesión segura agregando un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento secundario al [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="2f813-125">Specify how the client is authenticated while the secure session is established by adding a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element to the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="2f813-126">Especifique cómo se autentica el cliente estableciendo el atributo `authenticationMode`.</span><span class="sxs-lookup"><span data-stu-id="2f813-126">Specify how the client is authenticated by setting the `authenticationMode` attribute.</span></span>  
  
        ```xml  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5. <span data-ttu-id="2f813-127">Especifique la codificación de mensajes agregando un elemento de codificación, como [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) .</span><span class="sxs-lookup"><span data-stu-id="2f813-127">Specify the message encoding by adding an encoding element, such as [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
        ```xml  
        <textMessageEncoding />  
        ```  
  
    6. <span data-ttu-id="2f813-128">Especifique el transporte agregando un elemento de transporte, como [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="2f813-128">Specify the transport by adding a transport element, such as the [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
        ```xml  
        <httpTransport />  
        ```  
  
     <span data-ttu-id="2f813-129">El ejemplo de código siguiente utiliza la configuración para especificar un enlace personalizado que los mensajes puedan utilizar con SCT con estado en una sesión segura.</span><span class="sxs-lookup"><span data-stu-id="2f813-129">The following code example uses configuration to specify a custom binding that messages can use with stateful SCTs in a secure session.</span></span>  
  
    ```xml  
    <customBinding>  
      <binding name="StatefulSCTSecureSession">  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
          <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        </security>  
        <textMessageEncoding />  
        <httpTransport />  
      </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a><span data-ttu-id="2f813-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f813-130">Example</span></span>  
 <span data-ttu-id="2f813-131">El ejemplo de código siguiente crea un enlace personalizado que utiliza el modo de autenticación <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> para arrancar una sesión segura.</span><span class="sxs-lookup"><span data-stu-id="2f813-131">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 <span data-ttu-id="2f813-132">Cuando se usa la autenticación de Windows en combinación con un SCT con estado, WCF no rellena la <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> propiedad con la identidad del llamador real, sino que establece la propiedad en anónimo.</span><span class="sxs-lookup"><span data-stu-id="2f813-132">When Windows authentication is used in combination with a stateful SCT, WCF does not populate the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property with the actual caller's identity but instead sets the property to anonymous.</span></span> <span data-ttu-id="2f813-133">Dado que la seguridad de WCF debe volver a crear el contenido del contexto de seguridad del servicio para cada solicitud del SCT entrante, el servidor no realiza un seguimiento de la sesión de seguridad en la memoria.</span><span class="sxs-lookup"><span data-stu-id="2f813-133">Because WCF security must re-create the content of the service security context for every request from the incoming SCT, the server does not keep track of the security session in the memory.</span></span> <span data-ttu-id="2f813-134">Dado que es imposible serializar la instancia de <xref:System.Security.Principal.WindowsIdentity> en SCT, la propiedad <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> devuelve una identidad anónima.</span><span class="sxs-lookup"><span data-stu-id="2f813-134">Because it is impossible to serialize the <xref:System.Security.Principal.WindowsIdentity> instance into the SCT, the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property returns an anonymous identity.</span></span>  
  
 <span data-ttu-id="2f813-135">La siguiente configuración exhibe este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="2f813-135">The following configuration exhibits this behavior.</span></span>  
  
```xml  
<customBinding>  
  <binding name="Cancellation">  
       <textMessageEncoding />  
        <security
            requireSecurityContextCancellation="false">  
              <secureConversationBootstrap />  
        </security>  
    <httpTransport />  
  </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f813-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f813-136">See also</span></span>

- [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)
