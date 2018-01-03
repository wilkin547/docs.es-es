---
title: NetworkInformation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
caps.latest.revision: "5"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 897f094f512e423f055f0abea04d5403552ba31c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="networkinformation"></a>NetworkInformation
El espacio de nombres <xref:System.Net.NetworkInformation> permite recopilar información sobre eventos, cambios, estadísticas y propiedades de red. También se puede determinar si un host remoto es accesible mediante la clase <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType>.  
  
## <a name="network-availability-and-events"></a>Disponibilidad de la red y eventos  
 La clase <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> permite determinar si se ha cambiado la dirección de red o la disponibilidad. Para usar esta clase, cree un controlador de eventos para procesar el cambio y asócielo con un <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> o un <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>. Para más información, vea [Cómo: Detectar la disponibilidad de la red y los cambios de dirección](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md).  
  
## <a name="network-statistics-and-properties"></a>Estadísticas y propiedades de red  
 Puede recopilar estadísticas y propiedades de red por interfaz o protocolo. Las clases <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType> y <xref:System.Net.NetworkInformation.PhysicalAddress> ofrecen información sobre una interfaz de red determinada, mientras que las clases <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics> y <xref:System.Net.NetworkInformation.UdpStatistics> proporcionan información sobre los paquetes de la capa 3 y la capa 4. Para más información, vea [Cómo: Obtener información sobre el protocolo y la interfaz](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md).  
  
## <a name="determine-if-a-remote-host-is-reachable"></a>Determinar si un host remoto es accesible  
 Puede usar la clase <xref:System.Net.NetworkInformation.Ping> para determinar si un host remoto está funcionando en la red y es accesible. Para más información, vea [How to: Ping a Host](../../../docs/framework/network-programming/how-to-ping-a-host.md) (Cómo: hacer ping a un host).  
  
## <a name="see-also"></a>Vea también  
 [Network Programming Samples (Ejemplos de programación de red)](../../../docs/framework/network-programming/network-programming-samples.md)  
 [Ejemplo de tecnología de información de red](http://go.microsoft.com/fwlink/?LinkID=179564)  
 [NetStat Tool Technology Sample](http://go.microsoft.com/fwlink/?LinkID=179562) (Ejemplo de tecnología de la herramienta NetStat)  
 [Ping Client Technology Sample](http://go.microsoft.com/fwlink/?LinkID=179565) (Ejemplo de tecnología para hacer ping en un cliente)
