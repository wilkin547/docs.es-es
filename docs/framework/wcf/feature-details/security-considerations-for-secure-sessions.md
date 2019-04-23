---
title: Consideraciones de seguridad para sesiones seguras
ms.date: 03/30/2017
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
ms.openlocfilehash: d2244ba42b1cf95f77424d32a19ebe11dd3a2a45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148712"
---
# <a name="security-considerations-for-secure-sessions"></a>Consideraciones de seguridad para sesiones seguras
Debe tener en cuenta los siguientes elementos que afectan a la seguridad al implementar sesiones seguras. Para obtener más información acerca de las consideraciones de seguridad, consulte [consideraciones de seguridad](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md) y [prácticas recomendadas de seguridad](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
## <a name="secure-sessions-and-metadata"></a>Sesiones seguras y metadatos  
 Cuando se establece una sesión segura y la <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> propiedad está establecida en `false`, Windows Communication Foundation (WCF) envía un `mssp:MustNotSendCancel` aserción como parte de los metadatos en el documento de lenguaje de descripción de servicios Web (WSDL) para el punto de conexión de servicio. La aserción `mssp:MustNotSendCancel` informa a los clientes de que el servicio no responde a las solicitudes para cancelar la sesión segura. Cuando el <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> propiedad está establecida en `true`, a continuación, WCF no emite un `mssp:MustNotSendCancel` aserción en el documento WSDL. Se espera que los clientes envíen una solicitud de cancelación al servicio cuando dejen de necesitar la sesión segura. Cuando un cliente se genera mediante el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), el código de cliente reacciona adecuadamente a la presencia o ausencia de la `mssp:MustNotSendCancel` aserción.  
  
## <a name="secure-conversations-and-custom-tokens"></a>Conversaciones seguras y tokens personalizados  
 Hay algunos problemas con la mezcla de tokens personalizados y claves derivadas debido a la manera en que se define en la especificación WS-SecureConversation. La especificación dice que `wsse:SecurityTokenReference` es un elemento opcional que hace referencia al token derivado: "`/wsc:DerivedKeyToken/wsse:SecurityTokenReference` Este elemento opcional se utiliza para especificar tokens de contexto de seguridad, tokens de seguridad o la clave compartida o el secreto que se utilizan para la derivación. Si no se especifica, se supone que el destinatario puede determinar la clave compartida a partir del contexto del mensaje. Si no se puede determinar el contexto, a continuación, un error tal como `wsc:UnknownDerivationSource` debe emitirse. "  
  
 Esto significa que, si se desea derivar un token personalizado, se debería incluir el tipo de cláusula en un elemento `SecurityTokenReference`. Hay una opción para desactivar la derivación, pero el valor predeterminado es derivar las claves. Si no se incluye la clave, la serialización del token de clave derivado se realiza correctamente, pero, al intentar deserializarlo, se produce una excepción.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Deshabilitar las sesiones seguras en WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
- [Consideraciones de seguridad](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)
- [Procedimientos recomendados de seguridad](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)
