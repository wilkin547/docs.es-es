---
title: <claimTypeRequirements> (elemento)
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: 95cc1adf7ab37475e8d3eeb01750531a7f8ab249
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279635"
---
# <a name="claimtyperequirements-element"></a>\<claimTypeRequirements > elemento
Especifica una colección de tipos de notificación requeridos.  
  
 En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada. Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación. Cada elemento secundario de esta colección especifica los tipos de notificación necesarios y opcionales que se espera que aparezcan en una credencial aliada.  
  
 Un requisito de tipo de notificación está compuesto del URI del tipo de notificación solicitado en el token emitido junto con un parámetro booleano que indica si ese tipo de demanda se requiere en el token emitido o es opcional.  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [Funcionalidades de seguridad con enlaces personalizados](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)
- [Enlaces](../../../../../docs/framework/wcf/bindings.md)
- [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Seguridad de enlace personalizado](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
