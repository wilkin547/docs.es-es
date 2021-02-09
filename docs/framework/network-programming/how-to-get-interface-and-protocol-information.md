---
description: 'Más información acerca de: Procedimiento: para obtener información sobre el protocolo y la interfaz'
title: 'Cómo: obtener información sobre el protocolo y la interfaz'
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: fd88d26c-4063-495e-a253-736ac3e6b23f
ms.openlocfilehash: 8db91bbd556a3d145674b00cd017d7c068936995
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785775"
---
# <a name="how-to-get-interface-and-protocol-information"></a>Procedimiento para obtener información sobre el protocolo y la interfaz

En este ejemplo se muestra cómo leer las estadísticas TCP de una interfaz de red.  
  
## <a name="example"></a>Ejemplo  
  
```csharp
public static void ShowTcpStatistics(NetworkInterfaceComponent version)  
{  
    IPGlobalProperties properties =  
          IPGlobalProperties.GetIPGlobalProperties();  
    TcpStatistics tcpstat = null;  
    Console.WriteLine("");  
    switch (version)  
    {  
        case NetworkInterfaceComponent.IPv4:  
             tcpstat = properties.GetTcpIPv4Statistics();  
            Console.WriteLine("TCP/IPv4 Statistics:");  
            break;  
        case NetworkInterfaceComponent.IPv6:  
            tcpstat = properties.GetTcpIPv6Statistics();  
            Console.WriteLine("TCP/IPv6 Statistics:");  
            break;  
        default:  
            throw new ArgumentException("version");  
            break;  
    }  
    Console.WriteLine("  Minimum Transmission Timeout. : {0}",
        tcpstat.MinimumTransmissionTimeout);  
    Console.WriteLine("  Maximum Transmission Timeout. : {0}",
        tcpstat.MaximumTransmissionTimeout);  
  
    Console.WriteLine("  Connection Data:");  
    Console.WriteLine("      Current : {0}",
    tcpstat.CurrentConnections);  
    Console.WriteLine("      Cumulative : {0}",
        tcpstat.CumulativeConnections);  
    Console.WriteLine("      Initiated  : {0}",
        tcpstat.ConnectionsInitiated);  
    Console.WriteLine("      Accepted : {0}",
        tcpstat.ConnectionsAccepted);  
    Console.WriteLine("      Failed Attempts : {0}",
        tcpstat.FailedConnectionAttempts);  
    Console.WriteLine("      Reset : {0}",
        tcpstat.ResetConnections);  
  
    Console.WriteLine("");  
    Console.WriteLine("  Segment Data:");  
    Console.WriteLine("      Received  ................... : {0}",
        tcpstat.SegmentsReceived);  
    Console.WriteLine("      Sent : {0}",
        tcpstat.SegmentsSent);  
    Console.WriteLine("      Retransmitted : {0}",
        tcpstat.SegmentsResent);  
  
    Console.WriteLine("");  
}  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  

 Para este ejemplo se necesita:  
  
- Referencias al espacio de nombres **System.Net**.
