---
title: Crear solicitudes de Internet
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, sending and receiving data
- Networking
- HttpWebResponse class, sending and receiving data
- requesting data from Internet, creating requests
- Network Resources
- Internet, requesting data
- data requests, creating requests
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 201bc5e92aeedcbfe2f710681cf3bbc773a11424
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193387"
---
# <a name="creating-internet-requests"></a>Crear solicitudes de Internet
Las aplicaciones crean instancias <xref:System.Net.WebRequest> con el método <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>. Este es un método estático que crea una clase derivada de **WebRequest** según el esquema de URI que se ha pasado.  
  
## <a name="web-file-and-ftp-requests"></a>Web, archivos y solicitudes de FTP  
 .NET Framework proporciona la clase <xref:System.Net.HttpWebRequest>, que se deriva de **WebRequest**, para controlar las solicitudes HTTP y HTTPS. En la mayoría de los casos, la clase de **WebRequest** proporciona todas las propiedades que debe realizar una solicitud; en cambio, en caso necesario, puede convertir los objetos **WebRequest** creados por el método **WebRequest.Create** al tipo de **HttpWebRequest** para tener acceso a las propiedades específicas de HTTP de la solicitud. De igual forma, el objeto **HttpWebResponse** controla las respuestas de las solicitudes HTTP y HTTPS. Para tener acceso a las propiedades específicas de HTTP del objeto **HttpWebResponse**, necesita convertir los objetos **WebResponse** al tipo **HttpWebResponse**.  
  
 .NET Framework también proporciona las clases <xref:System.Net.FileWebRequest> y <xref:System.Net.FileWebResponse> para controlar las solicitudes de los recursos que usan el esquema de URI "file:". Igualmente, las clases <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse> se proporcionan para controlar las solicitudes de los recursos que usan el esquema "ftp:". Si la solicitud es para un recurso que usa cualquiera de estos esquemas, puede usar el método **WebRequest.Create** para obtener un objeto con el que realizar la solicitud.  
  
 Para controlar las solicitudes que usan otros protocolos de nivel de aplicación, debe implementar las clases específicas de protocolo derivadas de **WebRequest** y **WebResponse**. Para obtener más información, vea [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) (Programar protocolos acoplables).  
  
## <a name="see-also"></a>Vea también  
 [Cómo solicitar datos mediante la clase WebRequest](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)  
 [Solicitud de datos](../../../docs/framework/network-programming/requesting-data.md)
