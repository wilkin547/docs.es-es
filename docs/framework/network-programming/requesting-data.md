---
title: Solicitud de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sending data
- WebRequest class, sending and receiving data
- requesting data from Internet, about requesting data
- WebClient class, sending and receiving data
- network, requesting data
- receiving data
- sending data, about sending data
- response to Internet request, about responding to Internet requests
- data requests
- receiving data, about receiving data
- Internet, requesting data
ms.assetid: df6f1e1d-6f2a-45dd-8141-4a85c3dafe1d
ms.openlocfilehash: 1f367caf7656a83597b6262a5746686df15d33b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047315"
---
# <a name="requesting-data"></a>Solicitud de datos
El desarrollo de aplicaciones que se ejecutan en el entorno operativo distribuido de Internet hoy en día requiere un método eficaz y fácil de usar para recuperar datos de recursos de todo tipo. Los protocolos acoplables permiten desarrollar aplicaciones que usan una sola interfaz para recuperar datos de varios protocolos de Internet.  
  
## <a name="uploading-and-downloading-data-from-an-internet-server"></a>Cargar y descargar datos desde un servidor de Internet  
 Para transacciones simples de solicitud y respuesta, la clase <xref:System.Net.WebClient> proporciona el método más sencillo para cargar datos en un servidor de Internet o para descargarlos de él. **WebClient** proporciona métodos para cargar y descargar archivos, enviar y recibir secuencias, y enviar un búfer de datos al servidor y recibir una respuesta. **WebClient** usa las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> para establecer las conexiones reales con el recurso de Internet, por lo que cualquier protocolo acoplable registrado está disponible para su uso.  
  
 Las aplicaciones cliente que necesitan realizar transacciones más complejas solicitan datos de los servidores mediante la clase **WebRequest** y sus descendientes. **WebRequest** encapsula los detalles del proceso de conectar con el servidor, enviar la solicitud y recibir la respuesta. **WebRequest** es una clase abstracta que define un conjunto de propiedades y métodos que están disponibles para todas las aplicaciones que usan protocolos acoplables. Los descendientes de **WebRequest**, como <xref:System.Net.HttpWebRequest>, implementan las propiedades y los métodos definidos por **WebRequest** de una forma coherente con el protocolo subyacente.  
  
 La clase **WebRequest** crea instancias específicas de protocolo de descendientes de **WebRequest** mediante el uso del valor del URI pasado a su método <xref:System.Net.WebRequest.Create%2A> para determinar la instancia específica derivada de la clase que se va a crear. Las aplicaciones indican qué descendiente de **WebRequest** debe usarse para controlar una solicitud mediante el registro del constructor del descendiente con el método <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType>.  
  
 Se realiza una solicitud al recurso de Internet mediante una llamada al método <xref:System.Net.WebRequest.GetResponse%2A> en el elemento **WebRequest**. El método **GetResponse** construye la solicitud específica del protocolo a partir de las propiedades de **WebRequest**, establece la conexión de socket TCP o UDP con el servidor y envía la solicitud. Para las solicitudes que envían datos al servidor, como las solicitudes HTTP **Post** o FTP **Put**, el método <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> proporciona una secuencia de red en la que enviar los datos.  
  
 El método **GetResponse** devuelve un elemento **WebResponse** específico del protocolo que coincide con el elemento **WebRequest.**  
  
 **WebResponse** es también una clase abstracta que define propiedades y métodos que están disponibles para todas las aplicaciones que usan protocolos acoplables. Los descendientes de **WebResponse** implementan estas propiedades y métodos para el protocolo subyacente. La clase <xref:System.Net.HttpWebResponse>, por ejemplo, implementa la clase **WebResponse** para HTTP.  
  
 Los datos devueltos por el servidor se presentan a la aplicación en la secuencia devuelta por el método <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>. Puede usar esta secuencia como cualquier otra, como se muestra en el ejemplo siguiente.  
  
```csharp  
StreamReader sr =  
   new StreamReader(resp.GetResponseStream(), Encoding.ASCII);  
```  
  
```vb  
Dim sr As StreamReader  
sr = New StreamReader(resp.GetResponseStream(), Encoding.ASCII)  
```  
  
## <a name="see-also"></a>Vea también

- [Programación para redes en .NET Framework](index.md)
- [Cómo: solicitar una página web y recuperar los resultados como una secuencia](how-to-request-a-web-page-and-retrieve-the-results-as-a-stream.md)
- [Cómo: recuperar una WebResponse específica de protocolo que coincida con una WebRequest](how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest.md)
