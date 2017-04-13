---
title: "C&#243;mo: Crear un WSFederationHttpBinding | Microsoft Docs"
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
  - "federación"
  - "WCF, federación"
ms.assetid: e54897d7-aa6c-46ec-a278-b2430c8c2e10
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# C&#243;mo: Crear un WSFederationHttpBinding
En [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], la clase <xref:System.ServiceModel.WSFederationHttpBinding> proporciona un mecanismo para exponer un servicio federado, \([\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) en configuración\).  Es decir, un servicio que exige a los clientes su autenticación mediante un token de seguridad emitido por un servicio de token de seguridad.  Este tema muestra cómo configurar un <xref:System.ServiceModel.WSFederationHttpBinding> tanto en el código y como en la configuración.  Una vez creado el enlace, puede configurar un extremo para que utilice dicho enlace.  
  
 A continuación se describen los pasos básicos:  
  
1.  Seleccione un modo de seguridad.  <xref:System.ServiceModel.WSFederationHttpBinding> admite `Message`, que proporciona seguridad global en el nivel de mensaje, incluso a través de múltiples saltos, y `TransportWithMessageCredential`, que ofrece el mejor rendimiento para los casos en los que el cliente y el servicio pueden realizar una conexión directa sobre HTTPS.  
  
    > [!NOTE]
    >  <xref:System.ServiceModel.WSFederationHttpBinding> también admite `None` como modo de seguridad.  Este modo no es seguro y se ofrece solo para fines de depuración.  Si un extremo de servicio se implementa con un <xref:System.ServiceModel.WSFederationHttpBinding>, con su modo de seguridad establecido en `None`, el enlace de cliente resultante \(generado por [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)\) es <xref:System.ServiceModel.WsHttpBinding> con un modo de seguridad de `None`.  
  
     A diferencia de otros enlaces proporcionados por el sistema, no es necesario seleccionar un tipo de credencial de cliente cuando se utiliza `WSFederationHttpBinding`.  Esto es porque el tipo de credenciales de cliente siempre es un token emitido.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] adquiere un token de un emisor especificado y lo presenta al servicio para autenticar al cliente.  
  
2.  En clientes federados, se establece la propiedad <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerAddress%2A> para la dirección URL del servicio de token de seguridad.  Establezca <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerBinding%2A> como el enlace utilizado para comunicar con el servicio de token de seguridad.  
  
3.  Opcional.  Establezca la propiedad <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedTokenType%2A> en el Identificador uniforme de recursos \(URI\) de un tipo de token.  En servicios federados, especifique el tipo de token que el servicio espera.  En clientes federados, especifique el tipo de token que el cliente solicita al servicio de token de seguridad.  
  
     Si no se especifica ningún tipo de token, los clientes generan las solicitudes de tokens de seguridad \(RST\) de WS\-Trust sin un URI del tipo de token, y los servicios asumen que la autenticación del cliente se realiza utilizando, de manera predeterminada, un token de Lenguaje de marcado de aserción de seguridad \(SAML\) 1.1.  
  
     El URI para un token de SAML 1.1 es "http:\/\/docs.oasis\-open.org\/wss\/oasis\-wss\-saml\-token\-profile\-1.1\#SAMLV1.1".  
  
4.  Opcional.  En servicios federados, establezca la propiedad <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A> como la dirección URL de los metadatos de un servicio de token de seguridad.  Si el servicio está configurado para publicar metadatos, el extremo de los metadatos permite a los clientes del servicio seleccionar un par enlace\/extremo adecuado.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] la publicación de metadatos, vea [Publicación de metadatos](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
 También pueden establecerse otras propiedades, incluidos el tipo de clave utilizado como clave de prueba en el token emitido, el conjunto de algoritmos utilizado entre el cliente y el servicio, si negociar o especificar explícitamente la credencial del servicio, cualquier demanda concreta que el servicio espera que este contenido en el token emitido, y cualquier elemento XML adicional que deba agregarse a la solicitud que el cliente envía al servicio de token de seguridad.  
  
> [!NOTE]
>  La propiedad `NegotiateServiceCredential` es relevante únicamente cuando `SecurityMode` se establece como `Message`.  Si `SecurityMode` se establece como `TransportWithMessageCredential`, se omite la propiedad `NegotiateServiceCredential`.  
  
### Para configurar un WSFederationHttpBinding en código  
  
1.  Cree una instancia de <xref:System.ServiceModel.WSFederationHttpBinding>.  
  
2.  Establezca la propiedad <xref:System.ServiceModel.WSFederationHttpSecurity.Mode%2A> como <xref:System.ServiceModel.WSFederationHttpSecurityMode> o <xref:System.ServiceModel.WSFederationHttpSecurityMode>, según se requiera.  Si se requiere un conjunto de algoritmos distinto de <xref:System.ServiceModel.Security.SecurityAlgorithmSuite.Basic256%2A>, establezca la propiedad <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.AlgorithmSuite%2A> con un valor tomado de <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.  
  
3.  Establezca la propiedad <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.NegotiateServiceCredential%2A> según corresponda.  
  
4.  Establezca la propiedad <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedKeyType%2A> como <xref:System.IdentityModel.Tokens.SecurityKeyType> `SymmetricKey` o .`AsymmetricKey`, según se requiera.  
  
5.  Establezca un valor adecuado para la propiedad <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedTokenType%2A>.  Si no se establece ningún valor, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] toma el valor predeterminado "http:\/\/docs.oasis\-open.org\/wss\/oasis\-wss\-saml\-token\-profile\-1.1\#SAMLV1.1", lo que indica tokens de SAML 1.1.  
  
6.  Obligatorio en el cliente si no se especifica ningún emisor local; opcional en el servicio.  Cree <xref:System.ServiceModel.EndpointAddress> que contenga la dirección e información de identidad del servicio de token de seguridad, y asigne la instancia <xref:System.ServiceModel.EndpointAddress> a la propiedad <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerAddress%2A>.  
  
7.  Obligatorio en el cliente si no se especifica ningún emisor local; no se utiliza en el servicio.  Cree <xref:System.ServiceModel.Channels.Binding> para `SecurityTokenService`, y asigne la instancia <xref:System.ServiceModel.Channels.Binding> a la propiedad <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerBinding%2A>.  
  
8.  No se utiliza en el cliente; opcional en el servicio.  Cree una instancia <xref:System.ServiceModel.EndpointAddress> para los metadatos del servicio de token de seguridad, y asígnelo a la propiedad `IssuerMetadataAddress`.  
  
9. Opcional en el cliente y el servicio.  Cree y agregue una o más instancias <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement> a la colección devuelta por la propiedad <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>.  
  
10. Opcional en el cliente y el servicio.  Cree y agregue una o más instancias <xref:System.Xml.XmlElement> a la colección devuelta por la propiedad <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>.  
  
### Para crear un extremo federado en la configuración  
  
1.  Cree [\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) como elemento secundario del elemento [\<enlaces\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) en el archivo de configuración de la aplicación.  
  
2.  Cree [\<enlace\>](../../../../docs/framework/misc/binding.md) como elemento secundario de [\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md), y establezca el atributo `name` con un valor adecuado.  
  
3.  Cree un elemento `<security>` como elemento secundario del elemento de [\<enlace\>](../../../../docs/framework/misc/binding.md).  
  
4.  Establezca el atributo `mode` del elemento `<security>``Message con un valor de` `TransportWithMessageCredential o` , como se requiera.  
  
5.  Cree un elemento `<message>``<security> como elemento secundario del elemento` .  
  
6.  Opcional.  Establezca el atributo `algorithmSuite` del elemento `<message>` con un valor adecuado.  De manera predeterminada, es `Basic256`.  
  
7.  Opcional.  Si se requiere una clave de prueba asimétrica, establezca el atributo `issuedKeyType` del elemento `<message>``AsymmetricKey como` .  De manera predeterminada, es `SymmetricKey`.  
  
8.  Opcional.  Establezca el atributo `issuedTokenType` en el elemento `<message>`.  
  
9. Obligatorio en el cliente si no se especifica ningún emisor local; opcional en el servicio.  Cree un elemento `<issuer>` como elemento secundario del elemento `<message>`.  
  
10. Establezca el atributo `address` como el elemento `<issuer>`, y especifique la dirección en la que el servicio de token de seguridad acepta las solicitudes de token.  
  
11. Opcional.  Agregue un elemento secundario `<identity>` y especifique la identidad del servicio de token de seguridad  
  
12. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Identidad del servicio y autenticación](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
13. Obligatorio en el cliente si no se especifica ningún emisor local; no se utiliza en el servicio.  Cree un elemento [\<enlace\>](../../../../docs/framework/misc/binding.md) en la sección de enlaces que pueda usarse para comunicar con el servicio de token de seguridad.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo crear un enlace, vea [Cómo: Especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
14. Especifique el enlace creado en el paso anterior estableciendo los atributos `bindingConfiguration` y `binding` del elemento `<issuer>`.  
  
15. No se utiliza en el cliente; opcional en el servicio.  Cree un elemento `<issuerMetadata>` como elemento secundario del elemento \<`message`\>.  A continuación, en un atributo `address` del elemento `<issuerMetadata>`, especifique la dirección en la que el servicio de token de seguridad publicará sus metadatos.  De manera opcional, agregue un elemento secundario `<identity>` y especifique la identidad del servicio de token de seguridad  
  
16. Opcional en el cliente y el servicio.  Agregue un elemento `<claimTypeRequirements>``<message> como elemento secundario del elemento` .  Especifique las notificaciones obligatorias y opcionales en las que se basa el servicio agregando los elementos [\<agregar\>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)`<claimTypeRequirements>``claimType` al elemento , y definiendo el tipo de notificación con el atributo .  Especifique si una notificación determinada es obligatoria u opcional estableciendo el atributo `isOptional`.  
  
## Ejemplo  
 El ejemplo de código siguiente muestra el código para configurar `WSFederationHttpBinding` de manera imperativa.  
  
 [!code-csharp[c_FederationBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federationbinding/cs/source.cs#2)]
 [!code-vb[c_FederationBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federationbinding/vb/source.vb#2)]  
  
## Vea también  
 [Federación](../../../../docs/framework/wcf/feature-details/federation.md)   
 [Ejemplo de federación](../../../../docs/framework/wcf/samples/federation-sample.md)   
 [Cómo deshabilitar sesiones seguras en WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)