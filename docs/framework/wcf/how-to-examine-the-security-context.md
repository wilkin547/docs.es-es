---
title: "C&#243;mo: Examinar el contexto de seguridad | Microsoft Docs"
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
  - "Clase Claimset"
  - "Clase ServiceSecurityContext"
  - "WCF, seguridad"
ms.assetid: 389b5a57-4175-4bc0-ada0-fc750d51149f
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# C&#243;mo: Examinar el contexto de seguridad
Al programar servicios [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], el contexto de seguridad de servicio le permite determinar los detalles sobre las demandas y credenciales del cliente y utilizadas para autenticarse con el servicio.Esto se hace utilizando las propiedades de la clase <xref:System.ServiceModel.ServiceSecurityContext>.  
  
 Por ejemplo, puede recuperar la identidad del cliente actual utilizando la propiedad <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> o <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>.Para determinar si el cliente es anónimo, utilice la propiedad <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A>.  
  
 También puede determinar qué demandas se están realizando en nombre del cliente recorriendo en iteraciones la colección de demandas en la propiedad <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>.  
  
### Obtención del contexto de seguridad actual  
  
-   Tenga acceso a la propiedad estática <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> para obtener el contexto de seguridad actual.Examine cualquiera de las propiedades del contexto actual de la referencia.  
  
### Determinación de la identidad del llamador  
  
1.  Imprima el valor de las propiedades <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> y <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>.  
  
### Análisis de las demandas de un llamador  
  
1.  Devuelva la clase <xref:System.IdentityModel.Policy.AuthorizationContext> actual.Utilice la propiedad <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> para devolver el contexto de seguridad de servicio actual, a continuación, devuelva el `AuthorizationContext` mediante la propiedad <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>.  
  
2.  Analice la colección de objetos de vueltos de <xref:System.IdentityModel.Claims.ClaimSet> mediante la propiedad <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> de la clase <xref:System.IdentityModel.Policy.AuthorizationContext>.  
  
## Ejemplo  
 El ejemplo siguiente imprime los valores de las propiedades <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> y <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> del contexto de seguridad actual y la propiedad <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>, el valor de recurso de la demanda, y la propiedad <xref:System.IdentityModel.Claims.Claim.Right%2A> de cada demanda en el contexto de seguridad actual.  
  
 [!code-csharp[c_PrincipalPermissionAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#4)]
 [!code-vb[c_PrincipalPermissionAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#4)]  
  
## Compilar el código  
 El código utiliza los espacios de nombres siguientes:  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.IdentityModel.Policy>  
  
-   <xref:System.IdentityModel.Claims>  
  
## Vea también  
 [Seguridad de servicios](../../../docs/framework/wcf/securing-services.md)   
 [Identidad del servicio y autenticación](../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)