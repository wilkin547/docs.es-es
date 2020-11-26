---
title: Ataques por repetición
ms.date: 03/30/2017
ms.assetid: 7a17e040-93cd-4432-81b9-9f62fec78c8f
ms.openlocfilehash: 4325b3747074f13cf02752f99b25fa02e4117b4c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239086"
---
# <a name="replay-attacks"></a>Ataques por repetición

Un *ataque de reproducción* se produce cuando un atacante copia una secuencia de mensajes entre dos partes y reproduce la secuencia a una o más entidades. A menos que se mitigue, el equipo objeto del ataque procesa la secuencia como mensajes legítimos, produciendo una gama de malas consecuencias, como pedidos redundantes de un elemento.  
  
## <a name="bindings-may-be-subject-to-reflection-attacks"></a>Los enlaces pueden estar sujetos a ataques de reflexión  

 Los *ataques de reflexión* se reproducen de vuelta a un remitente como si provinieran del receptor como respuesta. La *detección de reproducción* estándar en el mecanismo de Windows Communication Foundation (WCF) no controla automáticamente esto.  
  
 Los ataques de reflexión se mitigan de forma predeterminada porque el modelo de servicio de WCF agrega un identificador de mensaje firmado a los mensajes de solicitud y espera un `relates-to` encabezado firmado en los mensajes de respuesta. Por consiguiente, el mensaje de solicitud no se puede volver a reproducir como una respuesta. En los escenarios de mensaje confiables (RM) seguros, los ataques de reflexión se mitigan porque:  
  
- Los esquemas de la secuencia de creación y los del mensaje de respuesta de la secuencia de creación son diferentes.  
  
- Para las secuencias símplex, los mensajes de secuencias que envía el cliente no se pueden volver a reproducir porque el cliente no puede entender tales mensajes.  
  
- Para las secuencias dúplex, los dos Id. de secuencia deben ser únicos. Así, un mensaje de secuencia saliente no se puede volver a reproducir como un mensaje de secuencia de entrada (todos los encabezados de secuencia y cuerpos también se firman).  
  
 Los únicos enlaces que son susceptibles a los ataques de reflexión son aquellos sin WS-Addressing: los enlaces personalizados que tienen WS-Addressing deshabilitado y utilizan la seguridad basada en clave simétrica. El <xref:System.ServiceModel.BasicHttpBinding> no utiliza WS-Addressing de forma predeterminada, pero no utiliza la seguridad basada en clave simétrica de tal modo que puede ser vulnerable a este ataque.  
  
 La mitigación para los enlaces personalizados consiste no establecer el contexto de seguridad o requerir encabezados WS-Addressing.  
  
## <a name="web-farm-attacker-replays-request-to-multiple-nodes"></a>Batería de servidores web: El atacante vuelve a reproducir la solicitud en varios nodos  

 Un cliente utiliza un servicio que se implementa en una batería de servidores web. Un atacante vuelve a reproducir una solicitud que se envió de un nodo de la batería a otro nodo de la batería. Además, si se reinicia un servicio, se vacía la caché de repetición, lo que capacita a un atacante para volver a realizar la solicitud. (La caché contiene valores de firmas de mensajes utilizados y vistos con anterioridad y evita las repeticiones de modo que esas firmas solo se puedan utilizar una vez. Las memorias caché de repetición no se comparten en una batería de servidores web).  
  
 Las mitigaciones incluyen:  
  
- Utilice la seguridad de modo de mensaje con tokens de contexto de seguridad con estado (con o sin conversación segura habilitada). Para obtener más información, consulte [Cómo: crear un token de contexto de seguridad para una sesión segura](how-to-create-a-security-context-token-for-a-secure-session.md).  
  
- Configure el servicio para utilizar la seguridad de nivel de transporte.  
  
## <a name="see-also"></a>Vea también

- [Consideraciones sobre la seguridad](security-considerations-in-wcf.md)
- [Divulgación de información](information-disclosure.md)
- [Elevación de privilegios](elevation-of-privilege.md)
- [Denegación de servicio](denial-of-service.md)
- [Manipulación](tampering.md)
- [Escenarios no admitidos](unsupported-scenarios.md)
