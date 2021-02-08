---
description: 'Más información acerca de cómo: examinar el contexto de seguridad'
title: Procedimiento para examinar el contexto de seguridad
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceSecurityContext class
- WCF, security
- Claimset class
ms.assetid: 389b5a57-4175-4bc0-ada0-fc750d51149f
ms.openlocfilehash: e82491a877cf1f741767c91d1e7c304ba7676e6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779405"
---
# <a name="how-to-examine-the-security-context"></a>Procedimiento para examinar el contexto de seguridad

Al programar servicios Windows Communication Foundation (WCF), el contexto de seguridad del servicio le permite determinar los detalles sobre las credenciales del cliente y las notificaciones que se usan para autenticarse con el servicio. Esto se hace utilizando las propiedades de la clase <xref:System.ServiceModel.ServiceSecurityContext>.  
  
 Por ejemplo, puede recuperar la identidad del cliente actual utilizando la propiedad <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> o <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>. Para determinar si el cliente es anónimo, utilice la propiedad <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A>.  
  
 También puede determinar qué demandas se están realizando en nombre del cliente recorriendo en iteraciones la colección de demandas en la propiedad <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>.  
  
### <a name="to-get-the-current-security-context"></a>Obtención del contexto de seguridad actual  
  
- Tenga acceso a la propiedad estática <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> para obtener el contexto de seguridad actual. Examine cualquiera de las propiedades del contexto actual de la referencia.  
  
### <a name="to-determine-the-identity-of-the-caller"></a>Determinación de la identidad del llamador  
  
1. Imprima el valor de las propiedades <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> y <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>.  
  
### <a name="to-parse-the-claims-of-a-caller"></a>Análisis de las demandas de un llamador  
  
1. Devuelva la clase <xref:System.IdentityModel.Policy.AuthorizationContext> actual. Utilice la propiedad <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> para devolver el contexto de seguridad de servicio actual, a continuación, devuelva el `AuthorizationContext` mediante la propiedad <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>.  
  
2. Analice la colección de objetos de vueltos de <xref:System.IdentityModel.Claims.ClaimSet> mediante la propiedad <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> de la clase <xref:System.IdentityModel.Policy.AuthorizationContext>.  
  
## <a name="example"></a>Ejemplo  

 El ejemplo siguiente imprime los valores de las propiedades <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> y <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> del contexto de seguridad actual y la propiedad <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>, el valor de recurso de la demanda, y la propiedad <xref:System.IdentityModel.Claims.Claim.Right%2A> de cada demanda en el contexto de seguridad actual.  
  
 [!code-csharp[c_PrincipalPermissionAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#4)]
 [!code-vb[c_PrincipalPermissionAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#4)]  
  
## <a name="compiling-the-code"></a>Compilar el código  

 El código utiliza los espacios de nombres siguientes:  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.IdentityModel.Policy>  
  
- <xref:System.IdentityModel.Claims>  
  
## <a name="see-also"></a>Vea también

- [Seguridad de servicios](securing-services.md)
- [Identidad del servicio y autenticación](./feature-details/service-identity-and-authentication.md)
