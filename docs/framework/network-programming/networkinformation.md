---
title: "NetworkInformation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Red"
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# NetworkInformation
El espacio de nombres <xref:System.Net.NetworkInformation> permite recopilar información sobre eventos, cambios, estadísticas, y de la red.  También puede determinar si un host remoto es accesible mediante la clase de <xref:System.Net.NetworkInformation.Ping?displayProperty=fullName> .  
  
## Disponibilidad y eventos de red  
 La clase de <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=fullName> permite determinar si la dirección de red o la disponibilidad ha cambiado.  Para utilizar esta clase, cree un controlador de eventos para procesar el cambio, y asociarlo a <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> o <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>.  Para obtener más información, vea [Cómo: detectar la disponibilidad de la red y los cambios de dirección](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md).  
  
## Estadísticas de red y propiedades  
 Puede recopilar las estadísticas de red y las propiedades de una interfaz o una base de protocolo.  <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType>, y las clases de <xref:System.Net.NetworkInformation.PhysicalAddress> proporcionan información acerca de una interfaz de red concreta, mientras que <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics>, y las clases de <xref:System.Net.NetworkInformation.UdpStatistics> proporcionan información sobre los paquetes de nivel 3 y de nivel 4.  Para obtener más información, vea [Cómo: obtener información sobre el protocolo y la interfaz](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md).  
  
## Determine si un host remoto es Reachable  
 Puede utilizar la clase de <xref:System.Net.NetworkInformation.Ping> para determinar si un host remoto está hacia arriba, en la red, y accesible.  Para obtener más información, vea [Cómo: hacer ping a un Host](../../../docs/framework/network-programming/how-to-ping-a-host.md).  
  
## Vea también  
 [Ejemplos de programación de red](../../../docs/framework/network-programming/network-programming-samples.md)   
 [Ejemplo de la TI de red](http://go.microsoft.com/fwlink/?LinkID=179564)   
 [ejemplo de tecnología de la herramienta de Netstat](http://go.microsoft.com/fwlink/?LinkID=179562)   
 [Ping Client Technology Sample](http://go.microsoft.com/fwlink/?LinkID=179565)