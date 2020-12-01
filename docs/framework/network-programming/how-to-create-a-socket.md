---
title: Procedimiento para crear un socket
description: Obtenga información sobre cómo inicializar un socket para comunicarse con dispositivos remotos. Use la clase Socket para especificar la familia de direcciones, el tipo de socket y el tipo de protocolo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- Networking
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- Socket class, creating sockets
- Network Resources
- receiving data, sockets
- protocols, sockets
- Internet, sockets
- sockets, creating
ms.assetid: c64a049c-5981-43bc-a2dc-1851473589c7
ms.openlocfilehash: 9746b814188a4dc92463399542a6044501d0da12
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287402"
---
# <a name="how-to-create-a-socket"></a>Procedimiento para crear un socket

Para poder usar un socket a fin de comunicarse con dispositivos remotos, es necesario inicializarlo con la información del protocolo y de la dirección de red. El constructor para la clase <xref:System.Net.Sockets.Socket> tiene parámetros que especifican la familia de direcciones, el tipo de socket y el tipo de protocolo que el socket usa para establecer conexiones.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se crea un socket que se puede usar para comunicarse en una red basada en TCP/IP, como Internet.  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
```  
  
 Para usar UDP en lugar de TCP, cambie el tipo de protocolo, como en el ejemplo siguiente:  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
```  
  
 La enumeración <xref:System.Net.Sockets.AddressFamily> especifica las familias de direcciones estándar usadas por la clase **Socket** para resolver direcciones de red (por ejemplo, el miembro **AddressFamily.InterNetwork** especifica la familia de direcciones IP de versión 4).  
  
 La enumeración <xref:System.Net.Sockets.SocketType> especifica el tipo de socket (por ejemplo, el miembro **SocketType.Stream** indica un socket estándar para enviar y recibir datos con control de flujo).  
  
 La enumeración <xref:System.Net.Sockets.ProtocolType> especifica el protocolo de red que se va a usar al comunicarse en el **Socket** (por ejemplo, **ProtocolType.Tcp** indica que el socket usa TCP y **ProtocolType.Udp** indica que el socket usa UDP).  
  
 Una vez que se ha creado un **socket**, puede iniciar una conexión con un punto de conexión remoto o recibir conexiones procedentes de dispositivos remotos.  
  
## <a name="see-also"></a>Vea también

- [Uso de sockets de cliente](using-client-sockets.md)
- [Escuchas con sockets](listening-with-sockets.md)
