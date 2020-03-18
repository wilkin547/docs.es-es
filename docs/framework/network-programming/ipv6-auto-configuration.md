---
title: Configuración automática de IPv6
ms.date: 03/30/2017
ms.assetid: 581c1d21-1013-43a3-bf3e-2d9ead62b79c
ms.openlocfilehash: 95d9dce36c70b8f6c6b9f963c0842305a111d436
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047816"
---
# <a name="ipv6-auto-configuration"></a>Configuración automática de IPv6
Un objetivo importante para IPv6 es ser compatible con el nodo Plug and Play. Es decir, debería ser posible conectar un nodo en una red IPv6 y hacer que se configurase automáticamente sin intervención humana.  
  
## <a name="type-of-auto-configuration"></a>Tipo de configuración automática  
 IPv6 es compatible con los siguientes tipos de configuración automática:  
  
- **Configuración automática con estado**. Este tipo de configuración requiere cierto grado de intervención humana, ya que es necesario un servidor de Protocolo de configuración dinámica de host para IPv6 (DHCPv6) para la instalación y la administración de los nodos. El servidor DHCPv6 mantiene una lista de nodos a los que proporciona información de configuración. También mantiene información de estado para que el servidor sepa cuánto tiempo se usa cada dirección y cuándo podría estar disponible para su reasignación.  
  
- **Configuración automática sin estado**. Este tipo de configuración es adecuada para organizaciones pequeñas y usuarios individuales. En este caso, cada host determina sus direcciones a partir del contenido de los anuncios de enrutador recibidos. El uso del estándar IEEE EUI-64 para definir la parte del identificador de red de la dirección permite dar por supuesto que la dirección de host del vínculo es exclusiva.  
  
 Independientemente de cómo se determine la dirección, el nodo debe comprobar que su dirección potencial es única para el vínculo local. Para ello, envía un mensaje de convocatoria de vecino a la dirección potencial. Si el nodo recibe respuesta, sabe que la dirección ya está en uso y debe establecer otra dirección.  
  
## <a name="ipv6-mobility"></a>Movilidad de IPv6  
 La proliferación de dispositivos móviles ha introducido un nuevo requisito: un dispositivo debe poder cambiar de forma arbitraria las ubicaciones en Internet IPv6 y seguir manteniendo las conexiones existentes. Para proporcionar esta funcionalidad, se asigna a un nodo móvil una dirección principal en la que siempre se puede establecer contacto con él. Cuando el nodo móvil se encuentra en su ubicación principal, se conecta con el vínculo principal y usa su dirección principal. Cuando el nodo móvil cambia de ubicación, un agente principal, que normalmente es un enrutador, transmite los mensajes entre el nodo móvil y los nodos con los que se comunica.  
  
## <a name="see-also"></a>Vea también

- [Protocolo de Internet versión 6](internet-protocol-version-6.md)
- [Sockets](sockets.md)
