---
title: Mallas del mismo nivel
ms.date: 03/30/2017
ms.assetid: d93e312e-ac04-40f8-baea-5da1cacb546e
ms.openlocfilehash: afd9eae36f28c28b33b74c4456feb4ba8c91314d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493342"
---
# <a name="peer-meshes"></a>Mallas del mismo nivel
A *malla* es una colección con nombre (un gráfico interconectado) de los nodos del mismo nivel que pueden comunicarse entre ellos y que se identifican mediante un identificador de malla único. Cada nodo se conecta a varios nodos. En una malla correctamente conectada, siempre hay una ruta entre dos nodos dados, a una distancia en saltos relativamente corta entre los nodos de los bordes más lejanos, y la malla permanece conectada aun cuando se quitan algunos nodos o conexiones. Los nodos activos en la malla publican la información de su extremo con el Id. de malla pertinente para que otros pares puedan buscarlos.  
  
## <a name="characteristics-of-a-mesh-created-using-peer-channel"></a>Características de una malla creada mediante el canal del mismo nivel  
  
#### <a name="uniquely-identified"></a>Identificación única  
  
-   Un identificador único identifica cada malla. El nombre de la malla (o Id. de la malla) está en el mismo formato que un nombre de host del servidor de nombres de dominio (DNS). Como tal, este Id. de malla debe ser único para el cliente previsto de la aplicación dentro del ámbito de la resolución que se está usando. Un nombre común, como "MyFamilysPeers" o "KevinsPokerTable", puede chocar con facilidad con otros nombres de usuario y puede devolver información de extremo del mismo nivel imprevista, que podría provocar problemas de privacidad o aumentar la latencia de conexión. Una manera de evitar estos problemas puede ser agregar un identificador único a continuación del alias de la malla (por ejemplo, "KevinsPokerTable90210").  
  
#### <a name="message-flooding"></a>Distribución de mensajes  
  
-   La malla permite que se propaguen los mensajes de uno o más remitentes a todos los nodos del mismo nivel en la misma malla. Los mensajes distribuidos por los nodos del mismo nivel usan los encabezados especificados en el espacio de nombres de `http://schemas.microsoft.com/net/2006/05/peer`.  
  
#### <a name="optimized-connections"></a>Conexiones optimizadas  
  
-   Una malla de canal del mismo nivel se ajusta automáticamente a medida que los nodos se conectan y desconectan, garantizando que todos los nodos tengan una buena conectividad, con poca probabilidad de que se generen particiones (grupos de nodos aislados entre sí). Las conexiones en la malla también se optimizan dinámicamente según los patrones de tráfico actuales, para que así la latencia de mensaje del remitente al receptor sea lo más pequeña posible.  
  
#### <a name="popular-network-features-that-peer-channel-does-not-provide"></a>Características de red conocidas que el canal del mismo nivel no proporciona  
 Es importante tener en cuenta que hay características de red populares que el canal del mismo nivel no proporciona. Estas características, que se pueden compilar sobre el canal del mismo nivel, son:  
  
-   **Orden de los mensajes:** posible que los mensajes de un único origen no lleguen a todas las demás partes en el mismo orden o en el orden en que envía el origen. Las aplicaciones que requieren que los mensajes se entreguen en un cierto orden deben integrarlo en sus aplicaciones (por ejemplo, incluyendo un id. que aumente monotónicamente con todos los mensajes).  
  
-   **Mensajería de confianza:** canal del mismo nivel no incluye un mecanismo para garantizar la recepción de mensajes por todos los equipos del mismo nivel. Para garantizar la entrega del mensaje, debe escribir una capa de confiabilidad sobre el canal del mismo nivel.
