---
title: Consideraciones de seguridad para sesiones seguras
ms.date: 03/30/2017
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
ms.openlocfilehash: 587897cc296523e0bfd5a4d4fa50b1e145cb69fb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601054"
---
# <a name="security-considerations-for-secure-sessions"></a>Consideraciones de seguridad para sesiones seguras
Debe tener en cuenta los siguientes elementos que afectan a la seguridad al implementar sesiones seguras. Para obtener más información sobre las consideraciones de seguridad, vea [consideraciones de seguridad](security-considerations-in-wcf.md) y [prácticas recomendadas para la seguridad](best-practices-for-security-in-wcf.md).  
  
## <a name="secure-sessions-and-metadata"></a>Sesiones seguras y metadatos  
 Cuando se establece una sesión segura y la <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> propiedad se establece en `false` , Windows Communication Foundation (WCF) envía una `mssp:MustNotSendCancel` aserción como parte de los metadatos en el documento de lenguaje de descripción de servicios web (WSDL) para el extremo de servicio. La aserción `mssp:MustNotSendCancel` informa a los clientes de que el servicio no responde a las solicitudes para cancelar la sesión segura. Cuando la <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> propiedad está establecida en `true` , WCF no emite ninguna `mssp:MustNotSendCancel` aserción en el documento WSDL. Se espera que los clientes envíen una solicitud de cancelación al servicio cuando dejen de necesitar la sesión segura. Cuando se genera un cliente mediante la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md), el código de cliente reacciona correctamente a la presencia o ausencia de la `mssp:MustNotSendCancel` aserción.  
  
## <a name="secure-conversations-and-custom-tokens"></a>Conversaciones seguras y tokens personalizados  
 Hay algunos problemas con la mezcla de tokens personalizados y claves derivadas debido a la manera en que se define en la especificación WS-SecureConversation. La especificación indica que `wsse:SecurityTokenReference` es un elemento opcional que hace referencia al token derivado: " `/wsc:DerivedKeyToken/wsse:SecurityTokenReference` este elemento opcional se utiliza para especificar el token de contexto de seguridad, el token de seguridad o la clave compartida o el secreto utilizados para la derivación. Si no se especifica, se supone que el destinatario puede determinar la clave compartida a partir del contexto del mensaje. Si no se puede determinar el contexto, `wsc:UnknownDerivationSource` se debería generar un error como ".  
  
 Esto significa que, si se desea derivar un token personalizado, se debería incluir el tipo de cláusula en un elemento `SecurityTokenReference`. Hay una opción para desactivar la derivación, pero el valor predeterminado es derivar las claves. Si no se incluye la clave, la serialización del token de clave derivado se realiza correctamente, pero, al intentar deserializarlo, se produce una excepción.  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para deshabilitar sesiones seguras en WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
- [Consideraciones sobre la seguridad](security-considerations-in-wcf.md)
- [Procedimientos recomendados de seguridad](best-practices-for-security-in-wcf.md)
