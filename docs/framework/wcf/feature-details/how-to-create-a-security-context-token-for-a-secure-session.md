---
title: 'Cómo: Crear un token de contexto de seguridad para una sesión segura'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
caps.latest.revision: 14
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 579a980d8d71b5fe3e21e49e84a602b3be37eff1
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-create-a-security-context-token-for-a-secure-session"></a>Cómo: Crear un token de contexto de seguridad para una sesión segura
Mediante el uso de un token de contexto de seguridad con estado (SCT) en una sesión segura, la sesión puede soportar que el servicio se recicle. Por ejemplo, cuando un SCT sin estado se utiliza en una sesión segura y se restablece Internet Information Services (IIS), a continuación, se pierden los datos de la sesión que están asociados al servicio. Estos datos de la sesión incluyen una caché de token de SCT. Así, la próxima vez que un cliente envíe un SCT sin estado al servicio, se devuelve un error, porque no se puede recuperar la clave que está asociada a SCT. Si, sin embargo, se utiliza un SCT con estado, la clave que está asociada a SCT se contiene dentro de SCT. Dado que la clave se contiene dentro de SCT y, por tanto, dentro del mensaje, el reciclaje del servicio no afecta a la sesión segura. De forma predeterminada, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utiliza SCT sin estado en una sesión segura. En este tema se detalla cómo utilizar SCT con estado en una sesión segura.  
  
> [!NOTE]
>  Los SCT con estado no se puede utilizar en una sesión segura que implique un contrato que derive de <xref:System.ServiceModel.Channels.IDuplexChannel>.  
  
> [!NOTE]
>  Para las aplicaciones que utilizan SCT con estado en una sesión segura, la identidad del subproceso para el servicio debe ser una cuenta de usuario que tenga un perfil de usuario asociado. Cuando el servicio se ejecuta bajo una cuenta que no tiene un perfil de usuario, como `Local Service`, se puede producir una excepción.  
  
> [!NOTE]
>  Cuando se requiere la suplantación en Windows XP, utilice una sesión segura sin un SCT con estado. Cuando se utilizan SCT con estado con suplantación, se produce una <xref:System.InvalidOperationException>. Para obtener más información, consulte [escenarios no admitidos](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
### <a name="to-use-stateful-scts-in-a-secure-session"></a>Para utilizar SCT con estado en una sesión segura  
  
-   Cree un enlace personalizado que especifique que una sesión segura que utiliza un SCT con estado protege los mensajes SOAP.  
  
    1.  Definir un enlace personalizado, mediante la adición de un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) al archivo de configuración para el servicio.  
  
        ```xml  
        <customBinding>  
        ```  
  
    2.  Agregar un [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento secundario a la [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
         Especifique un nombre de enlace estableciendo el atributo `name` en un nombre único dentro del archivo de configuración.  
  
        ```xml  
        <binding name="StatefulSCTSecureSession">  
        ```  
  
    3.  Especifique el modo de autenticación para los mensajes enviados a y desde este servicio mediante la adición de un [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento secundario a la [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
         Especifique que se utiliza una sesión segura estableciendo el atributo `authenticationMode` en `SecureConversation`. Especifique que se utilizan SCT con estado estableciendo el atributo `requireSecurityContextCancellation` en `false`.  
  
        ```xml  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
        ```  
  
    4.  Especifique cómo se autentica el cliente mientras la sesión segura se establece mediante la adición de un [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento secundario a la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).  
  
         Especifique cómo se autentica el cliente estableciendo el atributo `authenticationMode`.  
  
        ```xml  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5.  Especificar la codificación del mensaje mediante la adición de un elemento de codificación, como [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).  
  
        ```xml  
        <textMessageEncoding />  
        ```  
  
    6.  Especificar el transporte, agregando un elemento de transporte, como el [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).  
  
        ```xml  
        <httpTransport />  
        ```  
  
     El ejemplo de código siguiente utiliza la configuración para especificar un enlace personalizado que los mensajes puedan utilizar con SCT con estado en una sesión segura.  
  
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
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente crea un enlace personalizado que utiliza el modo de autenticación <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> para arrancar una sesión segura.  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 Cuando la autenticación de Windows se utiliza en combinación con un SCT con estado, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no rellena la propiedad <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> con la identidad del llamador real, sino que en su lugar establece la propiedad en anónimo. Dado que la seguridad de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] debe recrear el contenido del contexto de seguridad de servicio para cada solicitud del SCT de entrada, el servidor no mantiene un seguimiento de la sesión de seguridad en la memoria. Dado que es imposible serializar la instancia de <xref:System.Security.Principal.WindowsIdentity> en SCT, la propiedad <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> devuelve una identidad anónima.  
  
 La siguiente configuración exhibe este comportamiento.  
  
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
  
## <a name="see-also"></a>Vea también  
 [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
