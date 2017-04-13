---
title: "Derivar de WebResponse | Microsoft Docs"
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
  - "Derivar de WebResponse"
ms.assetid: f11d4866-a199-4087-9306-a5a4c18b13db
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Derivar de WebResponse
La clase de <xref:System.Net.WebResponse> es una clase base abstracta que proporciona los métodos y propiedades básicos para crear una respuesta protocolo\- específica que ajusta el modelo de protocolo conectable de .NET Framework.  Las aplicaciones que utilizan la clase de <xref:System.Net.WebRequest> para solicitar datos de recursos reciben las respuestas en **WebResponse**.  Los descendientes Protocolo\- específicos de **WebResponse** debe implementar los miembros abstractos de la clase de **WebResponse** .  
  
 La clase asociada de **WebRequest** debe crear los descendientes de **WebResponse** .  Por ejemplo, las instancias de <xref:System.Net.HttpWebResponse> sólo se crean como resultado de llamar a <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=fullName> o <xref:System.Net.HttpWebRequest.EndGetResponse%2A?displayProperty=fullName>.  Cada **WebResponse** contiene el resultado de una solicitud a un recurso y no está diseñada reutilizar.  
  
## Propiedad de ContentLength  
 La propiedad de <xref:System.Net.WebResponse.ContentLength%2A> indica el número de bytes de los datos disponibles de la secuencia devuelta por el método de <xref:System.Net.WebResponse.GetResponseStream%2A> .  La propiedad de **ContentLength** no indica el número de bytes de encabezado o de información de metadatos que devuelve el servidor; sólo indica el número de bytes de datos en el recurso solicitado propio.  
  
## Propiedad ContentType  
 La propiedad de <xref:System.Net.WebResponse.ContentType%2A> proporciona la información especial que el protocolo necesita enviar al cliente para identificar el tipo de contenido enviada por el servidor.  Normalmente es el tipo de contenido de MIME de los datos devueltos.  
  
## Propiedad headers  
 La propiedad de <xref:System.Net.WebResponse.Headers%2A> contiene una colección arbitraria de pares de nombre\/valor de metadatos asociados a la respuesta.  Los metadatos requerido por el protocolo que se puede expresar como un par de nombre\/valor puede estar incluida en la propiedad de **Headers** .  
  
 No es necesario usar la propiedad de **Headers** para utilizar los metadatos del encabezado.  Los metadatos Protocolo\-específicos se pueden exponer como propiedades; por ejemplo, la propiedad de <xref:System.Net.HttpWebResponse.LastModified%2A?displayProperty=fullName> expone el encabezado HTTP de **Last\-Modified** .  Cuando expone metadatos de encabezado como una propiedad, no debe permitir que la misma propiedad se establezca mediante la propiedad de **Headers** .  
  
## Propiedad de ResponseUri  
 La propiedad de <xref:System.Net.WebResponse.ResponseUri%2A> contiene el URI del recurso que proporcionó realmente en la respuesta.  Para los protocolos que no admiten la redirección, **ResponseUri** será igual que la propiedad de <xref:System.Net.WebRequest.RequestUri%2A> de **WebRequest** que creó la respuesta.  Si el protocolo admite redirigir la solicitud, **ResponseUri** contendrá el URI de la respuesta.  
  
## Método Close  
 El método de <xref:System.Net.WebResponse.Close%2A> cierra cualquier conexión creada por la solicitud y la respuesta y limpia los recursos utilizados por la respuesta.  El método de **Cerrar** cierra cualquier instancia de secuencia utilizada por la respuesta, pero no produce una excepción si la secuencia de respuesta se cerró previamente por una llamada al método de <xref:System.IO.Stream.Close%2A?displayProperty=fullName> .  
  
## Método de GetResponseStream  
 El método de <xref:System.Net.WebResponse.GetResponseStream%2A> devuelve una secuencia que contiene la respuesta del recurso solicitado.  La secuencia de respuesta contiene sólo los datos devueltos por el recurso; cualquier encabezado o metadatos incluido en la respuesta se debe eliminar de la respuesta y exponer a la aplicación a través de las propiedades protocolo\- específicas o la propiedad de **Headers** .  
  
 La instancia de la secuencia devuelta por el método de **GetResponseStream** pertenece a la aplicación y puede cerrarla sin cerrar **WebResponse**.  De convención, llamar al método de **WebResponse.Close** también cierra la secuencia devuelta por **GetResponse**.  
  
## Vea también  
 <xref:System.Net.WebResponse>   
 <xref:System.Net.HttpWebResponse>   
 <xref:System.Net.FileWebResponse>   
 [Programar protocolos acoplables](../../../docs/framework/network-programming/programming-pluggable-protocols.md)   
 [Derivar de WebRequest](../../../docs/framework/network-programming/deriving-from-webrequest.md)