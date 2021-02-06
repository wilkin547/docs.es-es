---
description: 'Más información acerca de: comunicaciones básicas: canales de transporte HTTP/HTTPS'
title: 'Comunicaciones básicas: canales de transporte HTTP-HTTPS'
ms.date: 03/30/2017
ms.assetid: 6c0a23c9-a663-461c-bdab-58b4d3e23642
ms.openlocfilehash: 585e7511a8c3291c09b40f5895bd700534e6faad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99635914"
---
# <a name="core-communications-httphttps-transport-channels"></a>Comunicaciones básicas: canales de transporte HTTP/HTTPS

En este tema se enumeran todas las excepciones generadas por los canales HTTP/HTTPS de transporte Windows Communication Foundation (WCF).  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|DigestExplicitCredsImpersonationLevel|Se especificó el nivel de suplantación especificado. La autenticación implícita del HTTP solo admite el nivel de 'Suplantación' cuando se utiliza con una credencial explícita.|  
|FramingContentTypeMismatch|El tipo de contenido especificado no lo admitió el servicio especificado. Los enlaces de servicio y cliente puede que no coincidan.|  
|Hosting_SslSettingsMisconfigured|Los valores de Secure Sockets Layer para el servicio especificado no coinciden con los de Internet Information Services.|  
|HttpAuthSchemeAndClientCert|El generador de agentes de escucha de HTTPS se configuró para que requiera un certificado de cliente y el esquema de autenticación especificado. Sin embargo, solo se puede requerir una forma de autenticación de cliente al mismo tiempo.|  
|HttpReceiveFailure|Un error ocurrido al recibir la respuesta HTTP en lo especificado. El enlace del extremo de servicio puede que no use el protocolo HTTP. Otra posibilidad es que el servidor terminase un contexto de solicitud HTTP debido a un cierre del servicio. Vea los registros del servidor para obtener más detalles.|  
|HttpRegistrationAccessDenied|HTTP no puede registrar la Dirección URL especificada. El proceso no tiene derechos de acceso a este espacio de nombres (consulte [reservas de espacio de nombres, registros y enrutamiento](/windows/desktop/http/namespace-reservations-registrations-and-routing) para obtener detalles).|  
|HttpRegistrationAlreadyExists|HTTP no puede registrar la Dirección URL especificada. Otra aplicación ya registró esta dirección URL con HTTP.SYS.|  
|HttpRegistrationPortInUse|HTTP no puede registrar la dirección URL especificada porque otra aplicación está utilizando el puerto TCP especificado.|  
|HttpSendFailure|Un error producido al realizar la solicitud HTTP a los especificados. Asegúrese de que la causa no es la no coincidencia de los enlaces de seguridad. Asegúrese también de que el servicio no se configura para Secure Sockets Layer.|  
|MessageXmlProtocolError|Un problema se produjo con el XML que se recibió de la red. Vea la excepción interna para obtener más detalles.|  
|MissingContentType|El receptor devolvió un error que indica que el tipo de contenido faltaba en la solicitud a los especificados. Consulte la excepción interna para obtener más información.|  
|ProxyAuthenticationLevelMismatch|La credencial de autenticación del proxy HTTP especificó un requisito de autenticación mutua que es más estricto que el requisito para la autenticación del servidor de destino.|  
|ProxyImpersonationLevelMismatch|La credencial de autenticación del proxy HTTP especificó una restricción del nivel de suplantación que es más estricta que la restricción para la autenticación del servidor de destino.|  
|SecureChannelFailure|Un canal seguro no se puede establecer para Secure Socket Layer/Transport Layer Security con la autoridad especificada.|  
|TrustFailure|No se puede establecer una relación de confianza para el canal seguro de Secure Socket Layer/Transport Layer Security con la autoridad especificada.|  
|UseDefaultWebProxyCantBeUsedWithExplicitProxyAddress|No puede especificar una dirección proxy explícita ni UseDefaultWebProxy=true en su elemento HttpTransportBinding.|
