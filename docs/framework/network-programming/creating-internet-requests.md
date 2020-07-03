---
title: Crear solicitudes de Internet
description: Obtenga información sobre la manera en que las aplicaciones crean instancias de WebRequest con el método WebRequest.Create. Este método crea una clase derivada basada en el esquema de URI que se le ha pasado.
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
ms.openlocfilehash: 389c7bf5969eca4322aa680a6f28dec0b899709a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325637"
---
# <a name="create-internet-requests"></a>Creación de solicitudes de Internet

Las aplicaciones crean instancias <xref:System.Net.WebRequest> con el método <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>. <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> es un método estático que crea una clase derivada de <xref:System.Net.WebRequest> según el esquema de URI que se le ha pasado.  
  
## <a name="web-file-and-ftp-requests"></a>Solicitudes web, de archivos y FTP

.NET Framework proporciona la clase <xref:System.Net.HttpWebRequest>, que se deriva de `WebRequest`, para controlar las solicitudes HTTP y HTTPS. En la mayoría de los casos, la clase `WebRequest` proporciona todas las propiedades necesarias para realizar una solicitud; en cambio, si es necesario, puede convertir los objetos `WebRequest` creados por el método `WebRequest.Create` al tipo `HttpWebRequest` para tener acceso a las propiedades específicas de HTTP de la solicitud. De igual forma, el objeto `HttpWebResponse` controla las respuestas de las solicitudes HTTP y HTTPS. Para tener acceso a las propiedades específicas de HTTP del objeto `HttpWebResponse`, debe convertir objetos `WebResponse` al tipo `HttpWebResponse`.  
  
.NET Framework también proporciona las clases <xref:System.Net.FileWebRequest> y <xref:System.Net.FileWebResponse> para controlar las solicitudes de recursos que usan el esquema de URI "file:". Igualmente, las clases <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse> se proporcionan para controlar las solicitudes de los recursos que usan el esquema "ftp:". Si solicita un recurso que usa cualquiera de estos esquemas, puede usar el método `WebRequest.Create` para obtener un objeto con el que realizar la solicitud.  
  
Para controlar las solicitudes que usan otros protocolos de nivel de aplicación, implemente las clases específicas de protocolo derivadas de `WebRequest` y `WebResponse`. Para obtener más información, vea [Programar protocolos acoplables](programming-pluggable-protocols.md).  
  
## <a name="see-also"></a>Vea también

- [Cómo: Solicitar datos mediante la clase WebRequest](how-to-request-data-using-the-webrequest-class.md)
- [Solicitud de datos](requesting-data.md)
