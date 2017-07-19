---
title: "C&#243;mo: Establecer el modo de seguridad | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Propiedad del modo"
  - "WCF, seguridad"
  - "WCF, Modo de seguridad"
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
caps.latest.revision: 22
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 22
---
# C&#243;mo: Establecer el modo de seguridad
La seguridad de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] tiene tres modos de seguridad comunes que se encuentran en la mayoría de los enlaces predefinidos: transporte, mensaje y “transporte con credencial del mensaje”. Dos modos adicionales son específicos para dos enlaces: el modo “solo credencial de transporte” encontrado en el <xref:System.ServiceModel.BasicHttpBinding>y el modo “Ambos” encontrado en el <xref:System.ServiceModel.NetMsmqBinding>.Sin embargo, este tema se concentra en los tres modos de seguridad comunes: <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.SecurityMode>y <xref:System.ServiceModel.SecurityMode>.  
  
 Tenga en cuenta que no todos los enlaces predefinidos admiten todos estos modos.Este tema establece el modo con las clases <xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.NetTcpBinding> y muestra cómo establecer el modo mediante programación y configuración.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] la seguridad de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], vea [Información general sobre seguridad](../../../docs/framework/wcf/feature-details/security-overview.md), [Seguridad de servicios](../../../docs/framework/wcf/securing-services.md) y [Protección de servicios y clientes](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).[!INCLUDE[crabout](../../../includes/crabout-md.md)] el modo de transporte y el mensaje, vea [Seguridad de transporte](../../../docs/framework/wcf/feature-details/transport-security.md) y [Seguridad de los mensajes](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).  
  
### Para establecer el modo de seguridad en código  
  
1.  Cree una instancia de la clase del enlace que está utilizando.Para obtener una lista de enlaces predefinidos, consulte [Enlaces proporcionados por el sistema](../../../docs/framework/wcf/system-provided-bindings.md).En el siguiente ejemplo se crea una instancia de la clase <xref:System.ServiceModel.WSHttpBinding>.  
  
2.  Establezca la propiedad `Mode` del objeto devuelto por la propiedad `Security`.  
  
     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]  
  
     De manera alternativa, establezca el modo en mensaje, como se muestra en el código siguiente.  
  
     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]  
  
     O establezca el modo en transporte con credenciales de mensaje, como se muestra en el código siguiente.  
  
     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]  
  
3.  También puede establecer el modo en el constructor del enlace, como se muestra en el código siguiente.  
  
     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]  
  
## Establecimiento de la propiedad la propiedad ClientCredentialType  
 El establecimiento del modo en uno de los tres valores determina cómo establece la propiedad `ClientCredentialType`.Por ejemplo, el uso de la clase <xref:System.ServiceModel.WSHttpBinding>, estableciendo el modo en `Transport` implica que debe establecer la propiedad <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> de la clase <xref:System.ServiceModel.HttpTransportSecurity> en un valor adecuado.  
  
#### Para establecer la propiedad ClientCredentialType para el modo de transporte  
  
1.  Cree una instancia del enlace.  
  
2.  Establezca la propiedad `Mode` en `Transport`.  
  
3.  Establezca la propiedad `ClientCredential` en un valor apropiado.El siguiente código establece la propiedad en `Windows`:  
  
     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]  
  
#### Para establecer la propiedad ClientCredentialType para el modo de mensaje  
  
1.  Cree una instancia del enlace.  
  
2.  Establezca la propiedad `Mode` en `Message`.  
  
3.  Establezca la propiedad `ClientCredential` en un valor apropiado.El siguiente código establece la propiedad en `Certificate`:  
  
     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]  
  
#### Para establecer el Modo y la propiedad ClientCredentialType en configuración  
  
1.  Agregue un elemento de enlace apropiado al elemento [\<enlaces\>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración.El siguiente ejemplo agrega un elemento [\<wsHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
2.  Agregue un elemento `<binding>``name y defina su atributo`  en un valor adecuado.  
  
3.  Agregue un elemento `<security>``mode y establezca el atributo` `Message en` `Transport,` `TransportWithMessageCredential o` .  
  
4.  Si se establece el modo en `Transport`, agregue un elemento `<transport>``clientCredential y establezca el atributo`  en un valor apropiado.  
  
     El siguiente ejemplo establece el modo en “`Transport"`, y, a continuación, establece el atributo `clientCredentialType` del `<transport>``Windows"` en “.  
  
    ```  
    <wsHttpBinding>  
    <binding name="TransportSecurity">  
        <security mode="Transport" />  
           <transport clientCredentialType = "Windows" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     De manera alternativa, establezca el `security mode` en "`Message"`, seguido por un elemento `<"message">`.Este ejemplo establece el `clientCredentialType` en "`Certificate"`.  
  
    ```  
    <wsHttpBinding>  
    <binding name="MessageSecurity">  
        <security mode="Message" />  
           <message clientCredentialType = "Certificate" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     Utilizar el valor <xref:System.ServiceModel.BasicHttpSecurityMode> es un caso especial y se explica más adelante.  
  
### Uso de TransportWithMessageCredential  
 Al establecer el modo de seguridad en `TransportWithMessageCredential`, el transporte determina el mecanismo real que proporciona la seguridad de nivel de transporte.Por ejemplo, el protocolo HTTP utiliza Secure Sockets Layer \(SSL\) sobre HTTP \(HTTPS\).Por consiguiente, se omite el establecimiento de la propiedad `ClientCredentialType` de cualquier objeto de seguridad de transporte \(como <xref:System.ServiceModel.HttpTransportSecurity>\).En otras palabras, solo puede establecer el `ClientCredentialType` del objeto de seguridad del mensaje \(para el enlace `WSHttpBinding`, el objeto <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>\).  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Cómo utilizar seguridad de transporte y credenciales de mensajes](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md).  
  
## Vea también  
 [Cómo: Configurar un puerto con un certificado SSL](../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)   
 [Cómo utilizar seguridad de transporte y credenciales de mensajes](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)   
 [Seguridad de transporte](../../../docs/framework/wcf/feature-details/transport-security.md)   
 [Seguridad de los mensajes](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)   
 [Información general sobre seguridad](../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Enlaces proporcionados por el sistema](../../../docs/framework/wcf/system-provided-bindings.md)   
 [\<seguridad\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)   
 [\<seguridad\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)   
 [\<seguridad\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)