---
title: 'Cómo: Crear un SecurityBindingElement para un modo de autenticación especificado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
author: BrucePerlerMS
ms.openlocfilehash: 6204a2832bbdc0c6631903687fcd8a1c45b35d03
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48036968"
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a>Cómo: Crear un SecurityBindingElement para un modo de autenticación especificado
Windows Communication Foundation (WCF) proporciona varios modos en que los clientes y servicios autentican entre sí. Puede crear los elementos de enlace de seguridad para estos modos de autenticación utilizando los métodos estáticos en la clase <xref:System.ServiceModel.Channels.SecurityBindingElement> o a través de la configuración, como se muestra en el ejemplo siguiente.  
  
 Para obtener más información acerca de los 18 modos de autenticación, consulte [modos de autenticación de SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra los métodos para crear los enlaces para los diferentes modos de autenticación.  
  
> [!NOTE]
>  Una vez creada una instancia del objeto <xref:System.ServiceModel.Channels.SecurityBindingElement>, varias propiedades son inmutables, como <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> y <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>. El hecho de llamar a `set` en tales propiedades, no las cambia.  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 [Modos de autenticación de SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 [Creación de un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
