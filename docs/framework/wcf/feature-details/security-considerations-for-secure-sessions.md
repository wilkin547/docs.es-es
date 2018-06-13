---
title: Consideraciones de seguridad para sesiones seguras
ms.date: 03/30/2017
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: f4ee56204d6980f412b9781868714dedb3c2675c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497495"
---
# <a name="security-considerations-for-secure-sessions"></a>Consideraciones de seguridad para sesiones seguras
Debe tener en cuenta los siguientes elementos que afectan a la seguridad al implementar sesiones seguras. Para obtener más información acerca de las consideraciones de seguridad, consulte [consideraciones de seguridad](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md) y [prácticas recomendadas de seguridad](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
## <a name="secure-sessions-and-metadata"></a>Sesiones seguras y metadatos  
 Cuando se establece una sesión segura y la <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> propiedad está establecida en `false`, Windows Communication Foundation (WCF) envía una `mssp:MustNotSendCancel` aserción como parte de los metadatos en el documento de lenguaje de descripción de servicios Web (WSDL) para el extremo de servicio. La aserción `mssp:MustNotSendCancel` informa a los clientes de que el servicio no responde a las solicitudes para cancelar la sesión segura. Cuando el <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> propiedad está establecida en `true`, a continuación, WCF no emite un `mssp:MustNotSendCancel` aserción en el documento WSDL. Se espera que los clientes envíen una solicitud de cancelación al servicio cuando dejen de necesitar la sesión segura. Cuando un cliente se genera mediante el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), el código de cliente responde correctamente a la presencia o ausencia de la `mssp:MustNotSendCancel` aserción.  
  
## <a name="secure-conversations-and-custom-tokens"></a>Conversaciones seguras y tokens personalizados  
 Hay algunos problemas con la mezcla de tokens personalizados y claves derivadas debido a la manera en que se define en la especificación WS-SecureConversation. La especificación dice que `wsse:SecurityTokenReference` es un elemento opcional que hace referencia el token derivado: "`/wsc:DerivedKeyToken/wsse:SecurityTokenReference` este elemento opcional se utiliza para especificar el token de contexto de seguridad, el token de seguridad o la clave/secreto compartido utilizado para la derivación. Si no se especifica, se supone que el destinatario puede determinar la clave compartida a partir del contexto del mensaje. Si no se puede determinar el contexto, a continuación, un error tal como `wsc:UnknownDerivationSource` debe emitirse. "  
  
 Esto significa que, si se desea derivar un token personalizado, se debería incluir el tipo de cláusula en un elemento `SecurityTokenReference`. Hay una opción para desactivar la derivación, pero el valor predeterminado es derivar las claves. Si no se incluye la clave, la serialización del token de clave derivado se realiza correctamente, pero, al intentar deserializarlo, se produce una excepción.  
  
## <a name="see-also"></a>Vea también  
 [Deshabilitar sesiones seguras en WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 [Consideraciones de seguridad](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Procedimientos recomendados de seguridad](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)
