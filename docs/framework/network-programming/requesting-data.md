---
title: "Solicitud de datos | Microsoft Docs"
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
  - "enviar datos"
  - "WebRequest (clase), enviar y recibir datos"
  - "solicitar datos de Internet, acerca de la solicitud de datos"
  - "WebClient (clase), enviar y recibir datos"
  - "redes, solicitar datos"
  - "recibir datos"
  - "enviar datos, acerca del envío de datos"
  - "respuesta a solicitud de Internet, acerca de cómo responder a solicitudes de Internet"
  - "solicitudes de datos"
  - "recibir datos, acerca de la recepción de datos"
  - "Internet, solicitar datos"
ms.assetid: df6f1e1d-6f2a-45dd-8141-4a85c3dafe1d
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Solicitud de datos
Desarrollar aplicaciones que se ejecutan en el entorno operativo enrutado internet de hoy requiere un método eficaz, fácil de usar para recuperar datos de los recursos de todos los tipos.  Los protocolos conectables permiten desarrollar aplicaciones que utilizan una sola interfaz para recuperar datos de protocolos de Internet.  
  
## Cargar y descargar datos de un servidor de Internet  
 Para las transacciones simples de solicitud y respuesta, la clase de <xref:System.Net.WebClient> proporciona el método más fácil para cargar datos a o descargar datos de un servidor de Internet.  **WebClient** proporciona métodos para cargar y descargar archivos, enviar y recibir secuencias, y enviar un búfer de datos al servidor y recibir una respuesta.  **WebClient** utiliza las clases de <xref:System.Net.WebRequest> y de <xref:System.Net.WebResponse> para crear conexiones reales al recurso de internet, por lo que cualquier protocolo conectable registrado está disponible para su uso.  
  
 Las aplicaciones cliente que necesita crear transacciones más complejas solicitan datos de los servidores mediante la clase de **WebRequest** y sus descendientes.  **WebRequest** encapsula los detalles de conexión con el servidor, de enviar la solicitud, y recibir la respuesta.  **WebRequest** es una clase abstracta que define un conjunto de propiedades y métodos que están disponibles para todas las aplicaciones que utilizan protocolos conectables.  Los descendientes de **WebRequest**, como <xref:System.Net.HttpWebRequest>, implementa las propiedades y los métodos definidos por **WebRequest** de manera que sea coherente con el protocolo subyacente.  
  
 La clase de **WebRequest** crea instancias protocolo\- específicas de los descendientes de **WebRequest** , utilizando el valor de URI pasado al método de <xref:System.Net.WebRequest.Create%2A> para determinar la instancia específica de la clase derivada para crear.  Las aplicaciones indican qué descendiente de **WebRequest** se debe utilizar para administrar una solicitud registrando el constructor descendientes con el método de <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=fullName> .  
  
 Una solicitud hace el recurso de internet llamando al método de <xref:System.Net.WebRequest.GetResponse%2A> en **WebRequest**.  El método de **GetResponse** construye la solicitud protocolo\- específica de las propiedades de **WebRequest**, crea el TCP o la conexión de socket UDP al servidor, y envía la solicitud.  Para las solicitudes que enviar datos al servidor, como solicitudes HTTP **Post** o FTP **Put** , el método de <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=fullName> proporciona una secuencia de red en el que se va a enviar los datos.  
  
 El método de **GetResponse** devuelve **WebResponse** protocolo\- específico que coincide con **WebRequest.**  
  
 La clase de **WebResponse** también es una clase abstracta que define las propiedades y métodos que están disponibles para todas las aplicaciones que utilizan protocolos conectables.  Los descendientes de**WebResponse** implementan estas propiedades y métodos para el protocolo subyacente.  La clase de <xref:System.Net.HttpWebResponse> , por ejemplo, implementa la clase de **WebResponse** para HTTP.  
  
 Los datos devueltos por el servidor se muestra la aplicación de la secuencia devuelta por el método de <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=fullName> .  Puede utilizar esta secuencia como cualquier otra, como se muestra en el ejemplo siguiente.  
  
```csharp  
StreamReader sr =  
   new StreamReader(resp.GetResponseStream(), Encoding.ASCII);  
  
```  
  
```vb  
Dim sr As StreamReader  
sr = New StreamReader(resp.GetResponseStream(), Encoding.ASCII)  
```  
  
## Vea también  
 [Programación para redes en .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Cómo: solicitar una página web y recuperar los resultados como una secuencia](../../../docs/framework/network-programming/how-to-request-a-web-page-and-retrieve-the-results-as-a-stream.md)   
 [Cómo: recuperar una WebResponse específica de protocolo que coincida con una WebRequest](../../../docs/framework/network-programming/how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest.md)