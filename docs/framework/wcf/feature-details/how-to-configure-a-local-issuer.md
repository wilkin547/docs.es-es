---
title: "C&#243;mo: Configurar un emisor local | Microsoft Docs"
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
ms.assetid: 15263371-514e-4ea6-90fb-14b4939154cd
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# C&#243;mo: Configurar un emisor local
En este tema se describe cómo configurar un cliente para utilizar un emisor local para los tokens emitidos.  
  
 A menudo, cuando un cliente se comunica con un servicio federado, el servicio especifica la dirección del servicio de token de seguridad que se espera que emita el token y que el cliente utilizará para autenticarse con el servicio federado.En algunas situaciones, el cliente se puede configurar para utilizar un *emisor local*.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utiliza un emisor local en casos donde la dirección del emisor de un enlace federado sea http:\/\/schemas.microsoft.com\/2005\/12\/ServiceModel\/Addressing\/Anonymous o `null`.En casos como éste, debe configurar <xref:System.ServiceModel.Description.ClientCredentials> con la dirección del emisor local y el enlace que se va a utilizar para comunicarse con ese emisor.  
  
> [!NOTE]
>  Si la propiedad <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> de la clase `ClientCredentials` está establecida en `true`, no se especifica una dirección del emisor local y la dirección del emisor especificada por [\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) u otro enlace federado es http:\/\/schemas.xmlsoap.org\/ws\/2005\/05\/identity\/issuer\/self, http:\/\/schemas.microsoft.com\/2005\/12\/ServiceModel\/Addressing\/Anonymous, o es `null`, a continuación, se usará el emisor [!INCLUDE[infocard](../../../../includes/infocard-md.md)] de Windows.  
  
### Para configurar el emisor local en código  
  
1.  Cree una variable de tipo <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
2.  Establezca la variable en la instancia devuelta de la propiedad <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> de la clase `ClientCredentials`.Esa instancia es devuelta por la propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> del cliente \(heredada de <xref:System.ServiceModel.ClientBase%601>\) o la propiedad <xref:System.ServiceModel.ChannelFactory.Credentials%2A> de <xref:System.ServiceModel.ChannelFactory>:  
  
     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]  
  
3.  Establezca la propiedad <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> en una nueva instancia de <xref:System.ServiceModel.EndpointAddress>, con la dirección del emisor local como un argumento para el constructor.  
  
     [!code-csharp[c_CreateSTS#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#10)]
     [!code-vb[c_CreateSTS#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#10)]  
  
     De manera alternativa, cree una nueva instancia <xref:System.Uri> como un argumento para el constructor.  
  
     [!code-csharp[c_CreateSTS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#11)]
     [!code-vb[c_CreateSTS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#11)]  
  
     El parámetro `addressHeaders` es una matriz de instancias de <xref:System.ServiceModel.Channels.AddressHeader>, tal como se muestra.  
  
     [!code-csharp[c_CreateSTS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#12)]
     [!code-vb[c_CreateSTS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#12)]  
  
4.  Establezca el enlace para el emisor local utilizando la propiedad <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A>.  
  
     [!code-csharp[c_CreateSTS#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#13)]
     [!code-vb[c_CreateSTS#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#13)]  
  
5.  Opcional.Agregue los comportamientos del extremo configurados para el emisor local agregando tales comportamientos a la colección devuelta por la propiedad <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A>.  
  
     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]  
  
### Para configurar el emisor local en la configuración  
  
1.  Cree un elemento [\<localIssuer\>](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)[\<issuedToken\>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)[\<clientCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md), que es a su vez un elemento secundario del elemento  en un comportamiento del extremo.  
  
2.  Establezca el atributo `address` en la dirección del emisor local que aceptará las solicitudes del token.  
  
3.  Establezca los atributos `bindingConfiguration` y `binding` en valores que hacen referencia al enlace adecuado que se debe usar cuando se comunica con el extremo del emisor local.  
  
4.  Opcional.Establezca el elemento [\<identidad\>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)\< `como elemento secundario del elemento localIssuer`\> y especifique la información de identidad para el emisor local.  
  
5.  Opcional.Establezca el elemento [\<encabezados\>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)\< `como elemento secundario del elemento localIssuer`\> y especifique los encabezados adicionales que son necesarios para dirigirse correctamente al emisor local.  
  
## Seguridad de .NET Framework  
 Tenga en cuenta que si se especifica una dirección y un enlace del emisor para un enlace determinado, el emisor local no se utiliza para los extremos que utilizan ese enlace.Los clientes que siempre esperan utilizar el emisor local deberían asegurarse de que no utilizan este enlace o que modifican el enlace de manera que la dirección del emisor sea `null`.  
  
## Vea también  
 [Cómo: Configurar las credenciales en un servicio de federación](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)   
 [Cómo crear un cliente federado](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [Cómo: Crear un WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)