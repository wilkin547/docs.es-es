---
title: Capacidades de seguridad con enlaces personalizados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9d252dca363c952dde44b499363e285d4bb7eb82
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="security-capabilities-with-custom-bindings"></a>Capacidades de seguridad con enlaces personalizados
Puede realizar las tareas de seguridad más habituales utilizando uno de los enlaces proporcionados por el sistema. Si necesita más control, sin embargo, puede crear un enlace personalizado con <xref:System.ServiceModel.Channels.SecurityBindingElement>, como se explica en estos temas. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]enlaces personalizados, consulte [enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Modos de autenticación de SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 Describe los modos de autenticación que son posibles con un enlace personalizado.  
  
 [Cómo: crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 Describe los pasos básicos para crear un enlace personalizado con un elemento de seguridad.  
  
 [Cómo: crear un SecurityBindingElement para un modo de autenticación especificado](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 Describe cómo crear un elemento de seguridad para un modo de autenticación especificado.  
  
 [Cómo: deshabilitar sesiones seguras en un WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 Describe cómo deshabilitar las sesiones seguras al crear un servicio de federación.  
  
 [Cómo: habilitar la detección de reproducción de mensaje](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 Describe cómo determinar cuándo se produce un ataque de reproducción.  
  
 [Cómo: crear una credencial de apoyo](../../../../docs/framework/wcf/feature-details/how-to-create-a-supporting-credential.md)  
 Describe cómo proporcionar una credencial de soporte a un servicio, si el servicio lo requiere.  
  
 [Cómo: configurar una confirmación de firma](../../../../docs/framework/wcf/feature-details/how-to-set-up-a-signature-confirmation.md)  
 Describe los pasos para confirmar las firmas al firmar digitalmente los mensajes.  
  
 [Cómo: conjunto un sesgo de reloj máximo](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)  
 Describe cómo establecer la diferencia horaria máxima permitida entre un servicio y un cliente.  
  
 [Cómo: deshabilitar el cifrado de firmas digitales](../../../../docs/framework/wcf/feature-details/how-to-disable-encryption-of-digital-signatures.md)  
 Describe cómo deshabilitar el cifrado de firmas digitales puede suponer una ventaja de rendimiento.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Descripción de los niveles de protección](../../../../docs/framework/wcf/understanding-protection-level.md)  
  
 [Protección de servicios y clientes](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a>Vea también  
 [Enlaces y seguridad](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md)
