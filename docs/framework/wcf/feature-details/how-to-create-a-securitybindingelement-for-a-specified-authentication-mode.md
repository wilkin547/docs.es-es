---
title: Procedimiento para crear un SecurityBindingElement para un modo de autenticación especificado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
ms.openlocfilehash: 7b71224c74d7e9e766fb17101219dc5718d5d6a6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286440"
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a>Procedimiento para crear un SecurityBindingElement para un modo de autenticación especificado

Windows Communication Foundation (WCF) proporciona varios modos en los que los clientes y servicios se autentican entre sí. Puede crear los elementos de enlace de seguridad para estos modos de autenticación utilizando los métodos estáticos en la clase <xref:System.ServiceModel.Channels.SecurityBindingElement> o a través de la configuración, como se muestra en el ejemplo siguiente.  
  
 Para obtener más información sobre los 18 modos de autenticación, consulte [modos de autenticación de SecurityBindingElement](securitybindingelement-authentication-modes.md).  
  
## <a name="example"></a>Ejemplo  

 El ejemplo de código siguiente muestra los métodos para crear los enlaces para los diferentes modos de autenticación.  
  
> [!NOTE]
> Una vez creada una instancia del objeto <xref:System.ServiceModel.Channels.SecurityBindingElement>, varias propiedades son inmutables, como <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> y <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>. El hecho de llamar a `set` en tales propiedades, no las cambia.  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Modos de autenticación de SecurityBindingElement](securitybindingelement-authentication-modes.md)
- [Procedimiento para crear un enlace personalizado mediante SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
