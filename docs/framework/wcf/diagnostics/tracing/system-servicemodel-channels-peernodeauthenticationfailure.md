---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.date: 03/30/2017
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
ms.openlocfilehash: cb7019f1e4b47bde7c98b0109afa7b0125b7ef63
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84577310"
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a>System.ServiceModel.Channels.PeerNodeAuthenticationFailure
El protocolo de enlace de seguridad con un vecino potencial no tuvo éxito.  
  
## <a name="description"></a>Descripción  
 Este seguimiento produce intentando establecer una conexión de vecino segura. Esto puede suceder debido a unas credenciales insuficientes o incorrectas.  
  
 PeerChannel reconoce un tipo de token único para una identificación fuerte, los certificados X.509, que proporcionan un modelo de identidad fuerte basados en el tipo de autenticación y autorización que se puede implementar. PeerChannel también proporciona compatibilidad para aplicaciones simples a través del uso de contraseñas. Las contraseñas solo se pueden utilizar para permitir la entrada a la sesión; no se pueden utilizar para realizar la autenticación de mensajes. Esto se debe a que es difícil e inadecuado utilizar un token simétrico que un grupo de iguales comparten para la autenticación de origen.  
  
## <a name="troubleshooting"></a>Solución de problemas  
 Asegúrese de que todos los vecinos tienen las credenciales de seguridad adecuadas.  
  
## <a name="see-also"></a>Vea también

- [Seguridad del canal del mismo nivel](../../feature-details/peer-channel-security.md)
- [Seguimiento](index.md)
- [Uso del seguimiento para solucionar problemas de su aplicación](using-tracing-to-troubleshoot-your-application.md)
- [Administración y diagnóstico](../index.md)
