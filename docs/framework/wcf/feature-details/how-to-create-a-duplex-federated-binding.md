---
title: "Procedimiento para crear un enlace federado d&#250;plex | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Procedimiento para crear un enlace federado d&#250;plex
<xref:System.ServiceModel.WSFederationHttpBinding> solo admite los contratos de intercambio de mensajes de datagrama y solicitud\/respuesta.Para utilizar el contrato de intercambio de mensajes dúplex, debe crear un enlace personalizado.Los procedimientos siguientes muestran cómo conseguirlo mediante configuración, utilizando la seguridad de modo de mensaje para los transportes TCP y HTTP, y la seguridad de modo mixto para el transporte TCP.El ejemplo de código donde se muestran los tres enlaces se encuentra al final de este tema.  
  
 También puede crear el enlace en el código.Para obtener una descripción de la pila de elementos de enlace que se deben crear, vea [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### Para crear un enlace personalizado federado dúplex con HTTP  
  
1.  En el nodo [\<enlaces\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)[\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
2.  Dentro del elemento [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)[\<enlace\>](../../../../docs/framework/misc/binding.md)`name` `con el atributo FederationDuplexHttpMessageSecurityBinding` establecido en .  
  
3.  Dentro del elemento [\<enlace\>](../../../../docs/framework/misc/binding.md)[\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)`authenticationMode` `con el atributo SecureConversation` establecido en .  
  
4.  Dentro del elemento [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)`authenticationMode` `con el atributo IssuedTokenForCertificate` `establecido en IssuedTokenForSslNegotiated` o .  
  
5.  Después del elemento [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<compositeDuplex\>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) vacío.  
  
6.  Después del elemento [\<compositeDuplex\>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) vacío.  
  
7.  Después del elemento [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<httpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) vacío.  
  
### Para crear un enlace personalizado federado dúplex con el modo de seguridad de mensajes TCP  
  
1.  En el nodo [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md).  
  
2.  Dentro del elemento [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)`name` `con el atributo FederationDuplexTcpMessageSecurityBinding` establecido en .  
  
3.  Dentro del elemento [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)`authenticationMode` `con el atributo SecureConversation` establecido en .  
  
4.  Dentro del elemento [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)`authenticationMode` `con el atributo IssuedTokenForCertificate` `establecido en IssuedTokenForSslNegotiated` o .  
  
5.  Después del elemento [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<tcpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) vacío.  
  
### Para crear un enlace personalizado federado dúplex con el modo de seguridad mixto TCP  
  
1.  En el nodo [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md).  
  
2.  Dentro del elemento [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)`name` `con el atributo FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` establecido en .  
  
3.  Dentro del elemento [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)`authenticationMode` `con el atributo SecureConversation` establecido en .  
  
4.  Dentro del elemento [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)`authenticationMode` `con el atributo IssuedTokenForCertificate` `establecido en IssuedTokenForSslNegotiated` o .  
  
5.  Después del elemento [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<sslStreamSecurity\>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) vacío.  
  
6.  Después del elemento [\<sslStreamSecurity\>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)[\<tcpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) vacío.  
  
## Ejemplo de código  
  
#### Ejemplo con tres enlaces  
  
1.  Inserte el código siguiente en su archivo de configuración.  
  
## Ejemplo  
  
```  
  
<bindings>  
   <customBinding>  
      <binding name="FederationDuplexHttpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <compositeDuplex />  
          <oneWay />  
          <httpTransport />  
       </binding>  
<!-- duplex over https is not supported -->  
       <binding name="FederationDuplexTcpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <tcpTransport />  
       </binding>              
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />  
          </security>  
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->  
          <sslStreamSecurity />  
          <tcpTransport />  
       </binding>              
    </customBinding>  
</bindings>  
  
```