---
title: "Escribir protocolos acoplables | Microsoft Docs"
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
  - "solicitudes de datos, protocolos acoplables"
  - "clase WebRequest, protocolos acoplables"
  - "respuesta a una solicitud de Internet, protocolos acoplables"
  - "URI"
  - "Windows Sockets"
  - "modelo de solicitud/respuesta"
  - "enviar datos, protocolos acoplables"
  - "protocolos acoplables"
  - "clase WebClient, acerca de la clase WebClient"
  - "protocolos acoplables, acerca de los protocolos acoplables"
  - "Internet, protocolos acoplables"
  - "identificadores de rutas de acceso"
  - "Identificador uniforme de recursos"
  - "desarrollo de aplicaciones [.NET Framework], protocolos acoplables"
  - "solicitar datos de Internet, protocolos acoplables"
  - "recibir datos, protocolos acoplables"
  - "protocolos, acoplables"
  - "identificadores de servidores"
  - "identificadores de esquemas"
ms.assetid: 4b48e22d-e4e5-48f0-be80-d549bda97415
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Escribir protocolos acoplables
Microsoft.NET framework proporciona una implementación por capas, extensible, y administrada de servicios de Internet que se pueden integrar rápida y fácilmente en las aplicaciones.  Las clases de acceso a Internet en <xref:System.Net> y espacios de nombres de <xref:System.Net.Sockets> se pueden utilizar para implementar las aplicaciones basadas Web\- y Herramienta de creación de HTML\- basadas en.  
  
## Aplicaciones de internet  
 Las aplicaciones de internet pueden clasificarse ampliamente en dos tipos: las aplicaciones cliente que solicitan información y las aplicaciones de servidor que respondan a información pregunte clientes.  Está World Wide Web la aplicación de servidor clásica de cliente de internet, donde los exploradores de uso de las personas tener acceso a los documentos y otros datos almacenados en los servidores web en todo el mundo.  
  
 Las aplicaciones no se limitan a una sola de estos roles; por ejemplo, el servidor de aplicaciones conocido de nivel intermedio responde a las solicitudes de clientes solicitando datos de otro servidor, en este caso actúa como un servidor y cliente.  
  
 La aplicación cliente realiza una solicitud identifica el recurso de internet solicitado y el protocolo de comunicación para usarla en la solicitud y respuesta.  Si es necesario, el cliente también proporciona cualquier dato adicional necesario para completar la solicitud, como ubicación de proxy o información de autenticación \(nombre de usuario, contraseña, etc.\).  La solicitud se forma una vez, la solicitud se puede enviar al servidor.  
  
## Identificador de recursos  
 .NET Framework utiliza un Identificador uniforme de recursos \(URI\) para identificar el recurso de internet y el protocolo de comunicación solicitados.  El URI contiene al menos tres, y posiblemente cuatro, fragmentos: el identificador de esquema, que identifica el protocolo de comunicaciones para la solicitud y la respuesta; el identificador del servidor, que consta de un nombre de host de \(DNS\) de Domain Name System o dirección TCP que identifica de forma única el servidor en internet; el identificador de la ruta, que busca la información solicitada en el servidor; y una cadena de consulta opcional, que pasa la información del cliente en el servidor.  Por ejemplo, ¿el URI “http:\/\/www.contoso.com\/whatsnew.aspx?date\=today” consta del identificador “http” de esquemas, el identificador “www.contoso.com” del servidor, la ruta de acceso “\/whatsnew.aspx”, y la cadena de consulta “? date\=today”.  
  
 Después de que el servidor ha recibido la solicitud y haya procesado la respuesta, devuelve la respuesta a la aplicación cliente.  La respuesta incluye información complementario, como el tipo de contenido \(texto sin formato o datos XML, por ejemplo\).  
  
## Solicitudes y respuestas en .NET Framework  
 Las clases específicas de las aplicaciones de .NET Framework para proporcionar los tres partes de información necesarios para obtener acceso a recursos de internet a través de un modelo de solicitud y respuesta: la clase de <xref:System.Uri> , que contiene el URI del recurso de internet está buscando; la clase de <xref:System.Net.WebRequest> , que contiene una solicitud para el recurso; y la clase de <xref:System.Net.WebResponse> , que proporciona un contenedor para la respuesta de entrada.  
  
 Las aplicaciones cliente crean instancias de `WebRequest` pasando el identificador URI del recurso de la red al método de <xref:System.Net.WebRequest.Create%2A> .  Este método estático crea `WebRequest` para un protocolo concreto, como HTTP.  `WebRequest` se devuelve que proporciona acceso a las propiedades que controlan la solicitud al servidor y acceso al flujo de datos se envía que cuando se realiza la solicitud.  El método de <xref:System.Net.WebRequest.GetResponse%2A> en `WebRequest` envía la solicitud de la aplicación cliente en el servidor identificado en el URI.  En los casos en los que la respuesta puede ser retrasada, la solicitud se puede hacer de forma asincrónica utilizando el método de <xref:System.Net.WebRequest.BeginGetResponse%2A> en **WebRequest**, y la respuesta se puede devolver en un momento posterior mediante el método de <xref:System.Net.WebRequest.EndGetResponse%2A> .  
  
 Los métodos de **GetResponse** y de **EndGetResponse** devuelven **WebResponse** que proporciona acceso a los datos devueltos por el servidor.  Puesto que los datos se proporciona para la aplicación que solicita como secuencia por el método de <xref:System.Net.WebResponse.GetResponseStream%2A> , se puede utilizar en flujos de datos de una aplicación donde se utiliza.  
  
 Las clases de **WebRequest** y de **WebResponse** son la base de protocolos conectables \(una implementación de servicios de red que permite desarrollar aplicaciones que utilizan recursos de internet sin preocuparse de los detalles específicos de protocolo de aplicaciones de que cada recurso.  Las clases descendientes de **WebRequest** se registran con la clase de **WebRequest** para controlar los detalles de crear conexiones reales a los recursos de internet.  
  
 Por ejemplo, la clase de <xref:System.Net.HttpWebRequest> administra los detalles de conexión con un recurso de internet mediante HTTP.  De forma predeterminada, cuando el método de **WebRequest.Create** encuentra un URI que comienza con “HTTP: ” o “https: ” \(identificadores de protocolo para HTTP y seguro HTTP\), **WebRequest** que se devuelve se puede utilizar tal cual, o se puede convertir a **HttpWebRequest** para tener acceso a las propiedades protocolo\- concretas.  En la mayoría de los casos, **WebRequest** proporciona toda la información necesaria para crear una solicitud.  
  
 Cualquier protocolo que se puede representar como una transacción de solicitud y respuesta se puede utilizar en **WebRequest**.  Puede derivar clases protocolo\- específicas de **WebRequest** y de **WebResponse** y después registrarlos para su uso en la aplicación con el método estático de <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=fullName> .  
  
 Cuando la autorización de cliente para las solicitudes de internet se requiere, la propiedad de <xref:System.Net.WebRequest.Credentials%2A> de **WebRequest** proporciona las credenciales necesarias.  Estas credenciales pueden ser pares de nombre sencillo y contraseña para HTTP autenticación implícita o básica, o un nombre y una contraseña y un dominio establecido en NTLM o la autenticación Kerberos.  Un conjunto de credenciales se puede almacenar en una instancia de [NetworkCredentials](frlrfsystemnetnetworkcredentialclasstopic) , o los conjuntos múltiples pueden almacenarse simultáneamente en una instancia de <xref:System.Net.CredentialCache> .  **CredentialCache** utiliza el URI de solicitud y el esquema de autenticación que el servidor admite para determinar qué credenciales a enviar al servidor.  
  
## Solicitudes simples con WebClient  
 Para las aplicaciones que necesitan realizar las solicitudes simples para los recursos de internet, la clase de <xref:System.Net.WebClient> proporciona métodos comunes para cargar datos a o descargar datos de un servidor de Internet.  **WebClient** se basa en la clase **WebRequest** para proporcionar acceso a los recursos de internet; por consiguiente, la clase de **WebClient** puede utilizar cualquier protocolo conectable registrado.  
  
 Para las aplicaciones que no pueden utilizar el modelo de solicitud y respuesta, o para las aplicaciones que necesitan escuchar en la red así como enviar solicitudes, el espacio de nombres **System.Net.Sockets** proporciona clases de [TCPClient](frlrfsystemnetsocketstcpclientclasstopic), de [TCPListener](frlrfsystemnetsocketstcplistenerclasstopic), y de [UDPClient](frlrfsystemnetsocketsudpclientclasstopic) .  Estas clases controlan los detalles del establecimiento de las conexiones mediante diferentes protocolos de transporte, y exponen la conexión de red a la aplicación como una secuencia.  
  
 Los desarrolladores familiarizados con Windows Sockets se comunican o los que necesitan un control proporcionado programando en el nivel de socket encontrarán que las clases de **System.Net.Sockets** satisfacen sus necesidades.  Las clases de **System.Net.Sockets** son un punto de transición de administrado a código nativo dentro de las clases de **System.Net** .  En la mayoría de los casos, **System.Net.Sockets** ordena datos de calcular las referencias en sus homólogos de 32 bits de Windows, así como administra las comprobaciones de seguridad necesaria.  
  
## Vea también  
 [Programar protocolos acoplables](../../../docs/framework/network-programming/programming-pluggable-protocols.md)   
 [Programación para redes en .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Ejemplos de programación de red](../../../docs/framework/network-programming/network-programming-samples.md)   
 [Los ejemplos de red para .NET en MSDN codifican la galería](http://code.msdn.microsoft.com/Wiki/View.aspx?ProjectName=nclsamples)