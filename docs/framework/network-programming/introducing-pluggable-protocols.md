---
title: Escribir protocolos acoplables
ms.date: 03/30/2017
helpviewer_keywords:
- data requests, pluggable protocols
- WebRequest class, pluggable protocols
- response to Internet request, pluggable protocols
- URI
- Windows Sockets
- request/response model
- sending data, pluggable protocols
- pluggable protocols
- WebClient class, about WebClient class
- pluggable protocols, about pluggable protocols
- Internet, pluggable protocols
- path identifiers
- Uniform Resource Identifier
- application development [.NET Framework], pluggable protocols
- requesting data from Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
- server identifiers
- scheme identifiers
ms.assetid: 4b48e22d-e4e5-48f0-be80-d549bda97415
ms.openlocfilehash: 72b47b8159f9f6f0dc3a19c5cbf94335507d9e7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047859"
---
# <a name="introducing-pluggable-protocols"></a>Escribir protocolos acoplables
Microsoft .NET Framework proporciona una implementación por capas, extensible y administrada de servicios de Internet que se puede integrar rápida y fácilmente en las aplicaciones. Las clases de acceso a Internet de los espacios de nombres <xref:System.Net> y <xref:System.Net.Sockets> se pueden usar para implementar aplicaciones basadas en Internet y en web.  
  
## <a name="internet-applications"></a>Aplicaciones de Internet  
 Las aplicaciones de Internet se pueden clasificar de forma general en dos tipos: aplicaciones de cliente que solicitan información y aplicaciones de servidor que responden a solicitudes de información de los clientes. La aplicación cliente-servidor de Internet clásica es la World Wide Web, donde las personas usan exploradores para obtener acceso a documentos y otros datos almacenados en servidores web de todo el mundo.  
  
 Las aplicaciones no se limitan a uno solo de estos roles. Por ejemplo, el familiar servidor de aplicaciones de nivel intermedio responde a las solicitudes de los clientes, para lo que solicita datos de otro servidor, en cuyo caso actúa como servidor y cliente.  
  
 La aplicación cliente realiza una solicitud, para lo que identifica el recurso de Internet solicitado y el protocolo de comunicación que se usará para la solicitud y la respuesta. Si es necesario, el cliente también proporciona todos los datos adicionales que sean necesarios para completar la solicitud, como la ubicación del proxy o la información de autenticación (nombre de usuario, contraseña, etc.). Una vez generada la solicitud, se puede enviar al servidor.  
  
## <a name="identifying-resources"></a>Identificación de recursos  
 .NET Framework usa un identificador uniforme de recursos (URI) para identificar el recurso de Internet solicitado y el protocolo de comunicación. El URI consta de al menos tres y, posiblemente, cuatro fragmentos: el identificador de esquema, que identifica el protocolo de comunicaciones para la solicitud y la respuesta; el identificador de servidor, que consta de un nombre de host del Sistema de nombres de dominio (DNS) o una dirección TCP que identifica de forma única el servidor en Internet; el identificador de la ruta de acceso, que busca la información solicitada en el servidor; y una cadena de consulta opcional, que pasa información del cliente al servidor. Por ejemplo, el URI `http://www.contoso.com/whatsnew.aspx?date=today` consta del identificador de esquema `http`, el identificador de servidor `www.contoso.com`, la ruta de acceso `/whatsnew.aspx` y la cadena de consulta `?date=today`.  
  
 Una vez que el servidor ha recibido la solicitud y procesado la respuesta, devuelve la respuesta a la aplicación cliente. La respuesta incluye información adicional, como el tipo de contenido (por ejemplo, texto sin formato o datos XML).  
  
## <a name="requests-and-responses-in-the-net-framework"></a>Solicitudes y respuestas en .NET Framework  
 .NET Framework usa clases específicas para proporcionar los tres elementos de información necesarios para obtener acceso a recursos de Internet a través de un modelo de solicitud/respuesta: la clase <xref:System.Uri>, que contiene el URI del recurso de Internet que se busca; la clase <xref:System.Net.WebRequest>, que contiene una solicitud para el recurso; y la clase <xref:System.Net.WebResponse>, que proporciona un contenedor para la respuesta entrante.  
  
 Las aplicaciones cliente crean instancias `WebRequest`, para lo que pasan el URI del recurso de red al método <xref:System.Net.WebRequest.Create%2A>. Este método estático crea una `WebRequest` para un protocolo específico, como HTTP. La `WebRequest` que se devuelve proporciona acceso a las propiedades que controlan la solicitud al servidor y el acceso al flujo de datos que se envía cuando se realiza la solicitud. El método <xref:System.Net.WebRequest.GetResponse%2A> de la `WebRequest` envía la solicitud de la aplicación cliente al servidor identificado en el URI. En los casos en los que la respuesta se retrasa, la solicitud se puede realizar de forma asincrónica con el método <xref:System.Net.WebRequest.BeginGetResponse%2A> en la **WebRequest**, y la respuesta se puede devolver más adelante mediante el método <xref:System.Net.WebRequest.EndGetResponse%2A>.  
  
 Los métodos **GetResponse** y **EndGetResponse** devuelven una **WebResponse** que proporciona acceso a los datos devueltos por el servidor. Dado que estos datos se proporcionan a la aplicación solicitante como un flujo mediante el método <xref:System.Net.WebResponse.GetResponseStream%2A>, se pueden usar en una aplicación en cualquier lugar en el que se usen flujos de datos.  
  
 Las clases **WebRequest** y **WebResponse** son la base de los protocolos acoplables, que consisten en una implementación de servicios de red que permite desarrollar aplicaciones que usan recursos de Internet sin preocuparse sobre los detalles específicos del protocolo que cada recurso usa. Las clases descendientes de **WebRequest** se registran con la clase **WebRequest** para administrar los detalles del establecimiento de conexiones a los recursos de Internet.  
  
 Por ejemplo, la clase <xref:System.Net.HttpWebRequest> administra los detalles de la conexión a un recurso de Internet mediante HTTP. De forma predeterminada, cuando el método **WebRequest.Create** encuentra un URI que empieza por "http:" o "https:" (identificadores de protocolo para HTTP y HTTP seguro), la **WebRequest** que se devuelve se puede usar tal cual o se puede convertir en **HttpWebRequest** para obtener acceso a propiedades específicas del protocolo. En la mayoría de los casos, la **WebRequest** proporciona toda la información necesaria para realizar una solicitud.  
  
 Todos los protocolos que se pueden representar como una transacción de solicitud/respuesta se pueden usar en una **WebRequest**. Puede derivar clases específicas del protocolo de **WebRequest** y de **WebResponse** y, después, registrarlas para que las use la aplicación con el método estático <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType>.  
  
 Cuando se requiere la autorización del cliente para las solicitudes de Internet, la propiedad <xref:System.Net.WebRequest.Credentials%2A> de la **WebRequest** proporciona las credenciales necesarias. Estas credenciales pueden ser un simple par de nombre y contraseña para la autenticación implícita o HTTP básico, o bien un conjunto de nombre, contraseña y dominio para la autenticación Kerberos o NTLM. Se puede almacenar un conjunto de credenciales en una instancia <xref:System.Net.NetworkCredential> o varios conjuntos simultáneamente en una instancia <xref:System.Net.CredentialCache>. **CredentialCache** usa el URI de la solicitud y el esquema de autenticación admitido por el servidor para determinar qué credenciales se deben enviar al servidor.  
  
## <a name="simple-requests-with-webclient"></a>Solicitudes sencillas con WebClient  
 Para las aplicaciones que necesitan realizar solicitudes sencillas de recursos de Internet, la clase <xref:System.Net.WebClient> proporciona métodos comunes para cargar datos en un servidor de Internet o descargarlos de él. **WebClient** se basa en la clase **WebRequest** para proporcionar acceso a recursos de Internet. Por lo tanto, la clase **WebClient** puede usar cualquier protocolo acoplable registrado.  
  
 Para las aplicaciones que no pueden usar el modelo de solicitud/respuesta o para las aplicaciones que necesitan escuchar en la red y enviar solicitudes, el espacio de nombres **System.Net.Sockets** proporciona las clases <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> y <xref:System.Net.Sockets.UdpClient>. Estas clases controlan los detalles del establecimiento de las conexiones mediante diferentes protocolos de transporte y exponen la conexión de red a la aplicación como un flujo.  
  
 Los programadores que están familiarizados con la interfaz de Windows Sockets o que necesitan el control que proporciona la programación en el nivel de socket constatarán que las clases **System.Net.Sockets** se adaptan a sus necesidades. Las clases **System.Net.Sockets** son una transición del código administrado al código nativo dentro de las clases **System.Net**. En la mayoría de los casos, las clases **System.Net.Sockets** serializan los datos en sus homólogos de 32 bits de Windows, además de controlar todas las comprobaciones de seguridad necesarias.  
  
## <a name="see-also"></a>Vea también

- [Programar protocolos acoplables](programming-pluggable-protocols.md)
- [Programación para redes en .NET Framework](index.md)
- [Ejemplos de programación de red](network-programming-samples.md)
