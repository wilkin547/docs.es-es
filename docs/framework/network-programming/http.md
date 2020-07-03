---
title: HTTP
description: Obtenga información sobre la compatibilidad total con HTTP que proporciona .NET Framework mediante el uso de las clases HttpWebRequest y HttpWebResponse.
ms.date: 03/30/2017
helpviewer_keywords:
- protocols, HTTP
- sending data, HTTP
- HttpWebResponse class, sending and receiving data
- HTTP
- receiving data, HTTP
- application protocols, HTTP
- Internet, HTTP
- network resources, HTTP
- HTTP, about HTTP
- HttpWebRequest class, sending and receiving data
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
ms.openlocfilehash: ffb7a5d027ef7691d03caf0ac45d4a3dd9bdb652
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502423"
---
# <a name="http"></a>HTTP
.NET Framework proporciona compatibilidad completa para el protocolo HTTP, que constituye la mayor parte de todo el tráfico de Internet, con las clases <xref:System.Net.HttpWebRequest> y <xref:System.Net.HttpWebResponse>. Estas clases, derivadas de <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse>, se devuelven de manera predeterminada siempre que el método estático <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> detecte un URI que comience por "http" o "https". En la mayoría de los casos, las clases **WebRequest** y **WebResponse** proporcionan todo lo necesario para realizar la solicitud, pero si necesita tener acceso a las características específicas de HTTP expuestas como propiedades, puede convertir estas clases en **HttpWebRequest** o **HttpWebResponse**.  
  
 **HttpWebRequest** y **HttpWebResponse** encapsulan una transacción de solicitud y respuesta HTTP estándar y proporcionan acceso a los encabezados HTTP comunes. Estas clases también admiten la mayoría de las características de HTTP 1.1, incluidas la canalización, envío y recepción de datos en fragmentos, autenticación, preautenticación, cifrado, compatibilidad de proxy, validación de certificados de servidor y administración de conexiones. Los encabezados y los encabezados personalizados que no se proporcionan mediante propiedades pueden almacenarse y se puede acceder a ellos mediante la propiedad **Headers**.  
  
 **HttpWebRequest** es la clase predeterminada que usa **WebRequest** y no necesita registrarse antes de que pueda pasar un URI al método **WebRequest.Create**.  
  
 Puede hacer que su aplicación siga las redirecciones de HTTP automáticamente estableciendo la propiedad <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> en **True** (el valor predeterminado). La aplicación redirigirá las solicitudes, y la propiedad <xref:System.Net.HttpWebResponse.ResponseUri%2A> de **HttpWebResponse** contendrá el recurso web actual que ha respondido a la solicitud. Si establece **AllowAutoRedirect** en **False**, su aplicación debe poder controlar las redirecciones como errores de protocolo HTTP.  
  
 Las aplicaciones reciben errores de protocolo HTTP capturando <xref:System.Net.WebException> con <xref:System.Net.WebException.Status%2A> establecido en <xref:System.Net.WebExceptionStatus>. La propiedad <xref:System.Net.WebException.Response%2A> contiene la **WebResponse** que ha enviado el servidor e indica el error HTTP actual que se ha detectado.  
  
## <a name="see-also"></a>Vea también

- [Acceso a Internet a través de un proxy](accessing-the-internet-through-a-proxy.md)
- [Usar protocolos de aplicaciones](using-application-protocols.md)
- [Cómo: Acceder a propiedades específicas de HTTP](how-to-access-http-specific-properties.md)
