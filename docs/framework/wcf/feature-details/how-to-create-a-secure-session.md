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
ms.workload: dotnet
ms.openlocfilehash: cd4f91ef5389dd4b8ecb63c1148d3a86918f2d10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-secure-session"></a>Cómo: Crear una sesión segura
Con la excepción de la [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) el enlace, los enlaces proporcionados por el sistema de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utilizar automáticamente las sesiones seguras cuando está habilitada la seguridad de los mensajes.  
  
 De forma predeterminada, las sesiones seguras no permanecen en ningún servidor reciclado. Cuando se establece una sesión segura, el cliente y el servicio almacenan en memoria caché la clave asociada a la sesión segura. Cuando se intercambian los mensajes, se intercambia solo un identificador de la clave almacenada en memoria caché. Si se recicla el servidor web, también se recicla la memoria en caché, de manera que el servidor web no puede recuperar la clave almacenada en memoria caché para el identificador. Si ocurre esto, se produce una excepción que se devuelve al cliente. Las sesiones seguras que usan un token de contexto de seguridad (SCT) con estado pueden sobrevivir en un servidor web que se recicle. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]uso de un SCT con estado en una sesión segura, consulte [Cómo: crear un Token de contexto de seguridad para una sesión segura](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a>Para especificar que un servicio utiliza las sesiones seguras utilizando uno de los enlaces proporcionados por el sistema  
  
-   Configure un servicio para utilizar un enlace proporcionado por el sistema que admite seguridad de mensaje.  
  
     Con la excepción de la [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) enlace, cuando los enlaces proporcionados por el sistema se configuran para utilizar la seguridad de mensaje, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa automáticamente las sesiones seguras. La siguiente tabla detalla los enlaces proporcionados por el sistema que admiten seguridad de mensaje y si la seguridad de mensaje es el mecanismo de seguridad predeterminado.  
  
    |Enlace proporcionado por el sistema|Elemento de configuración |Seguridad de mensaje activada de forma predeterminada|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|No|  
    |<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Sí|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Sí|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Sí|  
    |<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|No|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|No|  
  
     En el ejemplo de código siguiente se utiliza la configuración para especificar un enlace denominado `wsHttpBinding_Calculator` que usa el [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), seguridad de mensajes y proteger las sesiones.  
  
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
  
     En el ejemplo de código siguiente se especifica que la [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), seguridad de mensajes y proteger las sesiones se utilizan para proteger el `secureCalculator` service.  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  Las sesiones seguras pueden desactivarse para la [ <wsHttpBinding> ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) estableciendo la `establishSecurityContext` atribuir a `false`. Para los otros enlaces proporcionados por el sistema, las sesiones seguras pueden desactivarse solo mediante la creación un enlace personalizado.  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a>Especificar que un servicio utiliza sesiones seguras utilizando un enlace personalizado  
  
-   Cree un enlace personalizado que especifica que una sesión segura protege los mensajes SOAP.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]crear un enlace personalizado, vea [Cómo: personalizar un enlace proporcionados](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).  
  
     El ejemplo de código siguiente utiliza la configuración para especificar un enlace personalizado que envía mensajes utilizando una sesión segura.  
  
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
  
     El ejemplo de código siguiente crea un enlace personalizado que utiliza el modo de autenticación <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> para arrancar una sesión segura.  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre enlaces WCF](../../../../docs/framework/wcf/bindings-overview.md)
