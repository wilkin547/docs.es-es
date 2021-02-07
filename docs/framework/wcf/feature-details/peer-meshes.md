---
description: 'Más información acerca de: mallas del mismo nivel'
title: Mallas del mismo nivel
ms.date: 03/30/2017
ms.assetid: d93e312e-ac04-40f8-baea-5da1cacb546e
ms.openlocfilehash: bedb8931c4ed4c4f62cb3556699d7f9f07f6f022
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733390"
---
# <a name="peer-meshes"></a>Mallas del mismo nivel

Una *malla* es una colección con nombre (un gráfico interconectado) de nodos del mismo nivel que pueden comunicarse entre ellos y que se identifican mediante un identificador de malla único. Cada nodo se conecta a varios nodos. En una malla bien conectada, hay una ruta de acceso entre dos nodos cualesquiera, con relativamente pocos saltos entre los nodos de los bordes más alejados de la malla, y la malla permanecerá conectada incluso si se quitan algunos nodos o conexiones. Los nodos activos en la malla publican su información de punto de conexión con el identificador de malla correspondiente para que otros elementos del mismo nivel puedan encontrarlos.  
  
## <a name="characteristics-of-a-mesh-created-using-peer-channel"></a>Características de una malla creada mediante el canal del mismo nivel  
  
#### <a name="uniquely-identified"></a>Identificación única  
  
- Un identificador único identifica cada malla. El nombre de la malla (o Id. de la malla) está en el mismo formato que un nombre de host del servidor de nombres de dominio (DNS). Como tal, este Id. de malla debe ser único para el cliente previsto de la aplicación dentro del ámbito de la resolución que se está usando. Un nombre común, como "MyFamilysPeers" o "KevinsPokerTable", puede chocar con facilidad con otros nombres de usuario y puede devolver información de punto de conexión del mismo nivel imprevista, que podría provocar problemas de privacidad o aumentar la latencia de conexión. Una manera de evitar estos problemas puede ser agregar un identificador único a continuación del alias de la malla (por ejemplo, "KevinsPokerTable90210").  
  
#### <a name="message-flooding"></a>Distribución de mensajes  
  
- La malla permite que se propaguen los mensajes de uno o más remitentes a todos los nodos del mismo nivel en la misma malla. Los mensajes distribuidos por los nodos del mismo nivel usan los encabezados especificados en el espacio de nombres de `http://schemas.microsoft.com/net/2006/05/peer`.  
  
#### <a name="optimized-connections"></a>Conexiones optimizadas  
  
- Una malla de canal del mismo nivel se ajusta automáticamente a medida que los nodos se conectan y desconectan, garantizando que todos los nodos tengan una buena conectividad, con poca probabilidad de que se generen particiones (grupos de nodos aislados entre sí). Las conexiones en la malla también se optimizan dinámicamente según los patrones de tráfico actuales, para que así la latencia de mensaje del remitente al receptor sea lo más pequeña posible.  
  
#### <a name="popular-network-features-that-peer-channel-does-not-provide"></a>Características de red conocidas que el canal del mismo nivel no proporciona  

 Es importante tener en cuenta que hay características de red populares que el canal del mismo nivel no proporciona. Estas características, que se pueden compilar sobre el canal del mismo nivel, son:  
  
- **Ordenación de mensajes:** Los mensajes que se originan en un solo origen pueden no llegar a las demás partes en el mismo orden o en el orden en el que se envió el origen. Las aplicaciones que requieren que los mensajes se entreguen en un cierto orden deben integrarlo en sus aplicaciones (por ejemplo, incluyendo un id. que aumente monotónicamente con todos los mensajes).  
  
- **Mensajería de confianza:** El canal del mismo nivel no incluye un mecanismo para garantizar la recepción de mensajes por parte de todos los elementos del mismo nivel. Para garantizar la entrega del mensaje, debe escribir una capa de confiabilidad sobre el canal del mismo nivel.
