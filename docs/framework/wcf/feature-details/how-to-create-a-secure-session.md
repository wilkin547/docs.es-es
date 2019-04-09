---
title: Filtrar para crear una sesión segura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
ms.openlocfilehash: 4464100012fe9b3e1f0e8743707b1dc9a477c3d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205893"
---
# <a name="how-to-create-a-secure-session"></a>Filtrar para crear una sesión segura
Con la excepción de la [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) enlace, los enlaces proporcionados por el sistema en Windows Communication Foundation (WCF) utilizan automáticamente sesiones seguras cuando está habilitada la seguridad del mensaje.  
  
 De forma predeterminada, las sesiones seguras no permanecen en ningún servidor reciclado. Cuando se establece una sesión segura, el cliente y el servicio almacenan en memoria caché la clave asociada a la sesión segura. Cuando se intercambian los mensajes, se intercambia solo un identificador de la clave almacenada en memoria caché. Si se recicla el servidor web, también se recicla la memoria en caché, de manera que el servidor web no puede recuperar la clave almacenada en memoria caché para el identificador. Si ocurre esto, se produce una excepción que se devuelve al cliente. Las sesiones seguras que usan un token de contexto de seguridad (SCT) con estado pueden sobrevivir en un servidor web que se recicle. Para obtener más información acerca de cómo utilizar un SCT con estado en una sesión segura, consulte [Cómo: Crear un contexto de seguridad para una sesión segura Token](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a>Para especificar que un servicio utiliza las sesiones seguras utilizando uno de los enlaces proporcionados por el sistema  
  
-   Configure un servicio para utilizar un enlace proporcionado por el sistema que admite seguridad de mensaje.  
  
     Con la excepción de la [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) enlace, cuando se configuran los enlaces proporcionados por el sistema para usar automáticamente la seguridad de mensajes, WCF utiliza las sesiones seguras. La siguiente tabla detalla los enlaces proporcionados por el sistema que admiten seguridad de mensaje y si la seguridad de mensaje es el mecanismo de seguridad predeterminado.  
  
    |Enlace proporcionado por el sistema|Elemento de configuración |Seguridad de mensaje activada de forma predeterminada|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|No|  
    |<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Sí|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Sí|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Sí|  
    |<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|No|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|No|  
  
     En el ejemplo de código siguiente se usa la configuración para especificar un enlace denominado `wsHttpBinding_Calculator` que usa el [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), seguridad de mensajes y protección de las sesiones.  
  
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
  
     El ejemplo de código siguiente especifica que el [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), seguridad de mensajes y protección de las sesiones se utilizan para proteger el `secureCalculator` service.  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  Las sesiones seguras pueden desactivarse para el [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) estableciendo el `establishSecurityContext` atributo `false`. Para los otros enlaces proporcionados por el sistema, las sesiones seguras pueden desactivarse solo mediante la creación un enlace personalizado.  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a>Especificar que un servicio utiliza sesiones seguras utilizando un enlace personalizado  
  
-   Cree un enlace personalizado que especifica que una sesión segura protege los mensajes SOAP.  
  
     Para obtener más información acerca de cómo crear un enlace personalizado, vea [Cómo: Personalización de un enlace proporcionado por el sistema](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).  
  
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

- [Información general sobre enlaces WCF](../../../../docs/framework/wcf/bindings-overview.md)
