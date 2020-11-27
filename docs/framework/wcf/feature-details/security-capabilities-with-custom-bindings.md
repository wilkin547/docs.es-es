---
title: Capacidades de seguridad con enlaces personalizados
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 1b12907481ccb3f3c5f4b8aaba6ede8ebfa6228a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288312"
---
# <a name="security-capabilities-with-custom-bindings"></a>Capacidades de seguridad con enlaces personalizados

Puede realizar las tareas de seguridad más habituales utilizando uno de los enlaces proporcionados por el sistema. Si necesita más control, sin embargo, puede crear un enlace personalizado con <xref:System.ServiceModel.Channels.SecurityBindingElement>, como se explica en estos temas. Para obtener más información sobre los enlaces personalizados, vea [enlaces personalizados](../extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>En esta sección  

 [Modos de autenticación de SecurityBindingElement](securitybindingelement-authentication-modes.md)  
 Describe los modos de autenticación que son posibles con un enlace personalizado.  
  
 [Procedimiento para crear un enlace personalizado mediante SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 Describe los pasos básicos para crear un enlace personalizado con un elemento de seguridad.  
  
 [Procedimiento para crear un SecurityBindingElement para un modo de autenticación especificado](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 Describe cómo crear un elemento de seguridad para un modo de autenticación especificado.  
  
 [Procedimiento para deshabilitar sesiones seguras en WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 Describe cómo deshabilitar las sesiones seguras al crear un servicio de federación.  
  
 [Procedimiento para habilitar la detección de repetición de mensajes](how-to-enable-message-replay-detection.md)  
 Describe cómo determinar cuándo se produce un ataque de reproducción.  
  
 [Procedimiento para crear una credencial de apoyo](how-to-create-a-supporting-credential.md)  
 Describe cómo proporcionar una credencial de soporte a un servicio, si el servicio lo requiere.  
  
 [Procedimiento para establecer una confirmación de firma](how-to-set-up-a-signature-confirmation.md)  
 Describe los pasos para confirmar las firmas al firmar digitalmente los mensajes.  
  
 [Procedimiento para establecer un sesgo de reloj máximo](how-to-set-a-max-clock-skew.md)  
 Describe cómo establecer la diferencia horaria máxima permitida entre un servicio y un cliente.  
  
 [Procedimiento para deshabilitar el cifrado de firmas digitales](how-to-disable-encryption-of-digital-signatures.md)  
 Describe cómo deshabilitar el cifrado de firmas digitales puede suponer una ventaja de rendimiento.  
  
## <a name="reference"></a>Referencia  

 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Descripción de los niveles de protección](../understanding-protection-level.md)  
  
 [Protección de servicios y clientes](securing-services-and-clients.md)  
  
## <a name="see-also"></a>Vea también

- [Enlaces y seguridad](bindings-and-security.md)
- [Información general sobre seguridad](security-overview.md)
- [Enlaces proporcionados por el sistema](../system-provided-bindings.md)
