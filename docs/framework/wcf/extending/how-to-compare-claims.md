---
title: "C&#243;mo: Comparar notificaciones | Microsoft Docs"
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
  - "notificaciones [WCF]"
  - "notificaciones [WCF], comparar"
ms.assetid: 0c4ec84d-53df-408f-8953-9bc437f56c28
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# C&#243;mo: Comparar notificaciones
La infraestructura del modelo de identidad en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se utiliza para realizar la comprobación de autorización.Como tal, una tarea común es comparar las notificaciones en el contexto de autorización con las notificaciones necesarias para realizar la acción solicitada o tener acceso al recurso solicitado.En este tema se describe cómo comparar las notificaciones, incluidos los tipos de notificación integrados y personalizados.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] la infraestructura del modelo de identidad, vea [Administración de notificaciones y autorización con el modelo de identidad](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).  
  
 La comparación de notificaciones implica la comparación de las tres partes de una notificación \(tipo, derecho y recurso\) con las mismas partes de otra notificación para ver si son iguales.Vea el ejemplo siguiente.  
  
 [!code-csharp[c_CustomClaimComparison#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#9)]
 [!code-vb[c_CustomClaimComparison#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#9)]  
  
 Ambas notificaciones tienen un tipo de notificación <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, un derecho <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> y un recurso con la cadena "someone".Como las tres partes de la notificación son iguales, las notificaciones en sí mismas también lo son.  
  
 Los tipos de notificación integrados se comparan mediante el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>.Se utiliza el código de la comparación específico de la notificación allí donde sea necesario.Por ejemplo, dadas las siguientes dos notificaciones del nombre principal del usuario \(UPN\):  
  
 [!code-csharp[c_CustomClaimComparison#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#4)]
 [!code-vb[c_CustomClaimComparison#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#4)]  
  
 el código de la comparación en el método <xref:System.IdentityModel.Claims.Claim.Equals%2A> devuelve `true`, al suponer que `example\someone` identifica el mismo usuario de dominio que "someone@example.com."  
  
 Los tipos de notificación personalizados también se pueden comparar con el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>.Sin embargo, en los casos en que el tipo devuelto por la propiedad <xref:System.IdentityModel.Claims.Claim.Resource%2A> de la notificación es distinto a un tipo primitivo, <xref:System.IdentityModel.Claims.Claim.Equals%2A> solo devuelve `true` si los valores devueltos por las propiedades `Resource` son iguales de acuerdo con el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>.En los casos en que esto no sea adecuado, el tipo personalizado devuelto por la propiedad `Resource` debería invalidar los métodos <xref:System.IdentityModel.Claims.Claim.Equals%2A> y <xref:System.Object.GetHashCode%2A> para realizar el procesamiento personalizado que sea necesario.  
  
### Comparación de notificaciones integradas  
  
1.  Dadas dos instancias de la clase <xref:System.IdentityModel.Claims.Claim>, utilice <xref:System.IdentityModel.Claims.Claim.Equals%2A> para realizar la comparación, tal y como se muestra en el código siguiente.  
  
     [!code-csharp[c_CustomClaimComparison#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#5)]
     [!code-vb[c_CustomClaimComparison#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#5)]  
  
### Comparación de las notificaciones personalizadas con los tipos de recursos primitivos  
  
1.  En el caso de las notificaciones personalizadas con tipos de recursos primitivos, se puede realizar la comparación para las notificaciones integradas, tal y como se muestra en el código siguiente.  
  
     [!code-csharp[c_CustomClaimComparison#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#6)]
     [!code-vb[c_CustomClaimComparison#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#6)]  
  
2.  En el caso de las notificaciones con tipos de recursos basados en la estructura o la clase, el tipo de recurso debería invalidar el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>.  
  
3.  Primero compruebe si el parámetro `obj` es `null` y, en ese caso, devuelva `false`.  
  
     [!code-csharp[c_CustomClaimComparison#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#7)]
     [!code-vb[c_CustomClaimComparison#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#7)]  
  
4.  A continuación, llame a <xref:System.Object.ReferenceEquals%2A> y pase `this` y `obj` como parámetros.Si devuelve `true`, devuelva `true`.  
  
     [!code-csharp[c_CustomClaimComparison#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#8)]
     [!code-vb[c_CustomClaimComparison#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#8)]  
  
5.  Luego intente asignar `obj` a una variable local del tipo de clase.Si se produce un error, la referencia será `null`.En tales casos, devuelva `false`.  
  
6.  Realice la comparación personalizada necesaria para comparar correctamente la notificación actual con la notificación proporcionada.  
  
## Ejemplo  
 El ejemplo siguiente muestra una comparación de notificaciones personalizadas donde el recurso de la notificación es un tipo no primitivo.  
  
 [!code-csharp[c_CustomClaimComparison#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#0)]
 [!code-vb[c_CustomClaimComparison#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#0)]  
  
## Vea también  
 [Administración de notificaciones y autorización con el modelo de identidad](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)   
 [Cómo crear una notificación personalizada](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)