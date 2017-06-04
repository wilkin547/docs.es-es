---
title: "C&#243;mo: Crear una sesi&#243;n segura | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "seguridad [WCF], crear una sesión"
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# C&#243;mo: Crear una sesi&#243;n segura
Con la excepción del enlace [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), los enlaces proporcionados por el sistema en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utilizan automáticamente sesiones seguras cuando está habilitada la seguridad del mensaje.  
  
 De forma predeterminada, las sesiones seguras no permanecen en ningún servidor reciclado.  Cuando se establece una sesión segura, el cliente y el servicio almacenan en memoria caché la clave asociada a la sesión segura.  Cuando se intercambian los mensajes, se intercambia solo un identificador de la clave almacenada en memoria caché.  Si se recicla el servidor web, también se recicla la memoria en caché, de manera que el servidor web no puede recuperar la clave almacenada en memoria caché para el identificador.  Si ocurre esto, se produce una excepción que se devuelve al cliente.  Las sesiones seguras que usan un token de contexto de seguridad \(SCT\) con estado pueden sobrevivir en un servidor web que se recicle.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo usar SCT con estado en una sesión segura, vea [Cómo: Crear un token de contexto de seguridad para una sesión segura](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### Para especificar que un servicio utiliza las sesiones seguras utilizando uno de los enlaces proporcionados por el sistema  
  
-   Configure un servicio para utilizar un enlace proporcionado por el sistema que admite seguridad de mensaje.  
  
     Con la excepción del enlace [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), cuando se configuran los enlaces proporcionados por el sistema para utilizar seguridad de mensaje, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza automáticamente las sesiones seguras.  La siguiente tabla detalla los enlaces proporcionados por el sistema que admiten seguridad de mensaje y si la seguridad de mensaje es el mecanismo de seguridad predeterminado.  
  
    |Enlace proporcionado por el sistema|Elemento de configuración|Seguridad de mensaje activada de forma predeterminada|  
    |-----------------------------------------|-------------------------------|-----------------------------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|No|  
    |<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Sí|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Sí|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Sí|  
    |<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|No|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|No|  
  
     El ejemplo de código siguiente usa la configuración para especificar un enlace denominado `wsHttpBinding_Calculator` que usa [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), la seguridad de mensajes y las sesiones seguras.  
  
    ```  
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
  
     El ejemplo de código siguiente especifica que [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), seguridad de mensaje y sesiones seguras se utilizan para proteger el servicio `secureCalculator`.  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  Las sesiones seguras pueden desactivarse para [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) estableciendo el atributo `establishSecurityContext` en `false`.  Para los otros enlaces proporcionados por el sistema, las sesiones seguras pueden desactivarse solo mediante la creación un enlace personalizado.  
  
### Especificar que un servicio utiliza sesiones seguras utilizando un enlace personalizado  
  
-   Cree un enlace personalizado que especifica que una sesión segura protege los mensajes SOAP.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] crear un enlace personalizado, consulte [Personalización de un enlace proporcionado por el sistema](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).  
  
     El ejemplo de código siguiente utiliza la configuración para especificar un enlace personalizado que envía mensajes utilizando una sesión segura.  
  
    ```  
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
  
     El ejemplo de código siguiente crea un enlace personalizado que utiliza el modo de autenticación <xref:System.ServiceModel.Configuration.AuthenticationMode> para arrancar una sesión segura.  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## Vea también  
 [Información general de WCF Bindings](../../../../docs/framework/wcf/bindings-overview.md)