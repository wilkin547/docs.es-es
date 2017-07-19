---
title: "C&#243;mo: Crear un SecurityBindingElement para un modo de autenticaci&#243;n especificado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# C&#243;mo: Crear un SecurityBindingElement para un modo de autenticaci&#243;n especificado
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] proporciona varios modos por medio de los cuales los clientes y servicios se autentican entre sí.Puede crear los elementos de enlace de seguridad para estos modos de autenticación utilizando los métodos estáticos en la clase <xref:System.ServiceModel.Channels.SecurityBindingElement> o a través de la configuración, como se muestra en el ejemplo siguiente.  
  
 Para [!INCLUDE[crabout](../../../../includes/crabout-md.md)] los 18 modos de autenticación, vea [Modos de autenticación de SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).  
  
## Ejemplo  
 El ejemplo de código siguiente muestra los métodos para crear los enlaces para los diferentes modos de autenticación.  
  
> [!NOTE]
>  Una vez creada una instancia del objeto <xref:System.ServiceModel.Channels.SecurityBindingElement>, varias propiedades son inmutables, como <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> y <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.El hecho de llamar a `set` en tales propiedades, no las cambia.  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## Vea también  
 [Modos de autenticación de SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)   
 [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)