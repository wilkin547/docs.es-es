---
title: "C&#243;mo: Crear una identidad de entidad de seguridad personalizada | Microsoft Docs"
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
  - "IAuthorizationPolicy"
  - "IPrincipal"
  - "PrincipalPermissionAttribute"
  - "principalPermissionMode"
ms.assetid: c4845fca-0ed9-4adf-bbdc-10812be69b61
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# C&#243;mo: Crear una identidad de entidad de seguridad personalizada
<xref:System.Security.Permissions.PrincipalPermissionAttribute> es un medio declarativo para controlar el acceso a los métodos de servicio.  Al utilizar este atributo, la enumeración <xref:System.ServiceModel.Description.PrincipalPermissionMode> especifica el modo para realizar las comprobaciones de la autorización.  Cuando este modo está establecido en <xref:System.ServiceModel.Description.PrincipalPermissionMode>, permite al usuario especificar una clase <xref:System.Security.Principal.IPrincipal> personalizada devuelta por la propiedad <xref:System.Threading.Thread.CurrentPrincipal%2A>.  Este tema muestra el escenario cuando <xref:System.ServiceModel.Description.PrincipalPermissionMode> se utiliza en combinación con una directiva de autorización personalizada y una entidad de seguridad personalizada.  
  
 Para obtener más información sobre el uso de <xref:System.Security.Permissions.PrincipalPermissionAttribute>, consulte [Cómo restringir el acceso con la clase PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).  
  
## Ejemplo  
 [!code-csharp[PrincipalPermissionMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/principalpermissionmode/cs/source.cs#8)]
 [!code-vb[PrincipalPermissionMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/principalpermissionmode/vb/source.vb#8)]  
  
## Compilar el código  
 Hace referencia a los siguientes espacios de nombres necesarios para compilar el código:  
  
-   <xref:System>  
  
-   <xref:System.Collections.Generic>  
  
-   <xref:System.Security.Permissions>  
  
-   <xref:System.Security.Principal>  
  
-   <xref:System.Threading>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Description>  
  
-   <xref:System.IdentityModel.Claims>  
  
-   <xref:System.IdentityModel.Policy>  
  
## Vea también  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>   
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>   
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>   
 [Cómo: Utilizar el proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)   
 [Cómo restringir el acceso con la clase PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)