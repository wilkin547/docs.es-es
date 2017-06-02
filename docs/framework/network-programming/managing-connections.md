---
title: "Administrar conexiones | Microsoft Docs"
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
  - "Internet, conexiones"
  - "HTTP, clases para las conexiones"
  - "solicitar datos de Internet, conexiones"
  - "enviar datos, conexiones"
  - "recibir datos, conexiones"
  - "Clase ServicePoint, sobre la clase ServicePoint"
  - "respuesta a una solicitud de Internet, conexiones"
  - "conexiones [.NET Framework], clases"
  - "recursos de red, conexiones"
  - "descargar recursos de Internet, conexiones"
  - "clase ServicePointManager, sobre la clase ServicePointManager"
ms.assetid: 9b3d3de7-189f-4f7d-81ae-9c29c441aaaa
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Administrar conexiones
Las aplicaciones que utilizan HTTP para conectarse a los recursos de datos pueden utilizar las clases de <xref:System.Net.ServicePoint> y de <xref:System.Net.ServicePointManager> de.NET framework para administrar conexiones a internet y como ayuda para lograr la escala y el rendimiento óptimos.  
  
 La clase de **ServicePoint** proporciona una aplicación con un extremo que la aplicación pueda conectarse para tener acceso a recursos de internet.  Cada **ServicePoint** contiene información que ayuda optimizan conexiones con un servidor de Internet para compartir información de optimización entre conexiones para mejorar el rendimiento.  
  
 Cada **ServicePoint** es identificado por un Identificador uniforme de recursos \(URI\) y clasificadas según el identificador de esquema y fragmentos hospedados de URI.  Por ejemplo, la misma instancia de **ServicePoint** proporcionaría solicitudes a los URI http:\/\/www.contoso.com\/index.htm y http:\/\/www.contoso.com\/news.htm?date\=today puesto que tienen el mismo identificador de esquema \(HTTP\) y fragmentos de host \(www.contoso.com\).  Si la aplicación ya tiene una conexión persistente el servidor www.contoso.com, utiliza esa conexión para recuperar las solicitudes, evitando la necesidad de crear dos conexiones.  
  
 **ServicePointManager** es una clase estática que administra la creación y destrucción de las instancias de **ServicePoint** .  **ServicePointManager** crea **ServicePoint** cuando la aplicación solicita un recurso de internet que no está en la colección de instancias existentes de **ServicePoint** .  Se destruyen las instancias de**ServicePoint** cuando se ha superado el tiempo de inactividad máximo o cuando el número de instancias existentes de **ServicePoint** supera el número máximo de instancias de **ServicePoint** para la aplicación.  Puede controlar el tiempo de inactividad máximo predeterminado y el número máximo de instancias de **ServicePoint** estableciendo las propiedades de <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> y de <xref:System.Net.ServicePointManager.MaxServicePoints%2A> en **ServicePointManager**.  
  
 El número de conexiones entre un cliente y un servidor puede tener un serio impacto en el rendimiento de la aplicación.  De forma predeterminada, una aplicación mediante la clase de <xref:System.Net.HttpWebRequest> utiliza un máximo de dos conexiones persistentes a un servidor determinado, pero también puede establecer el número de conexiones máximo en función de la por\- aplicación.  
  
> [!NOTE]
>  Los límites de especificación HTTP\/1.1 el número de conexiones de una aplicación a dos conexiones por servidor.  
  
 El número óptimo de conexiones depende de las condiciones reales en las que se ejecuta la aplicación.  Aumentar el número de conexiones disponibles para la aplicación no puede afectar al rendimiento de la aplicación.  Para determinar el impacto de varias conexiones, pruebas de rendimiento de se ejecuta mientras varía el número de conexiones.  Puede cambiar el número de conexiones que una aplicación utilice cambiando la propiedad estática de <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> en la clase de **ServicePointManager** en la inicialización de aplicaciones, como se muestra en el ejemplo de código siguiente.  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 Cambiar la propiedad de **ServicePointManager.DefaultConnectionLimit** no afecta a las instancias inicializadas de **ServicePoint** .  El código siguiente muestra cómo cambiar el límite de la conexión en **ServicePoint** existente para el servidor http:\/\/www.contoso.com el valor almacenado en `newLimit`.  
  
```csharp  
Uri uri = new Uri("http://www.contoso.com/");  
ServicePoint sp = ServicePointManager.FindServicePoint(uri);  
sp.ConnectionLimit = newLimit;  
```  
  
```vb  
Dim uri As New Uri("http://www.contoso.com/")  
Dim sp As ServicePoint = ServicePointManager.FindServicePoint(uri)  
sp.ConnectionLimit = newLimit  
```  
  
## Vea también  
 [Agrupación de conexiones](../../../docs/framework/network-programming/connection-grouping.md)   
 [Usar protocolos de aplicaciones](../../../docs/framework/network-programming/using-application-protocols.md)