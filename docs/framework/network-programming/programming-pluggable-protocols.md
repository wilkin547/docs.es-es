---
title: "Programar protocolos acoplables | Microsoft Docs"
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
  - "descargar recursos de Internet, protocolos acoplables"
  - "clase WebRequest, protocolos acoplables"
  - "respuesta a una solicitud de Internet, protocolos acoplables"
  - "clase WebResponse, protocolos acoplables"
  - "enviar datos, protocolos acoplables"
  - "recursos de red, protocolos acoplables"
  - "Internet, protocolos acoplables"
  - "programar protocolos acoplables"
  - "protocolos acoplables, programación"
  - "solicitar datos de Internet, protocolos conectables"
  - "recibir datos, protocolos acoplables"
  - "protocolos, acoplables"
ms.assetid: 66ef8456-7576-4e97-8956-959b216373db
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Programar protocolos acoplables
<xref:System.Net.WebRequest> y clases abstractos de <xref:System.Net.WebResponse> proporcionan la base para los protocolos conectables.  Derivando clases protocolo\- específicas de <xref:System.Net.WebRequest> y de <xref:System.Net.WebResponse>, una aplicación puede solicitar datos de un recurso de internet y leer la respuesta sin especificar el protocolo utilizado.  
  
 Antes de crear <xref:System.Net.WebRequest>protocolo\- concreto, debe registrar el método Create.  Utilice el método estático de <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> de <xref:System.Net.WebRequest> para registrar un descendiente de <xref:System.Net.WebRequest> para controlar un conjunto de solicitudes a un esquema determinado de internet, un esquema y un servidor, o un esquema, un servidor, y en una ruta.  
  
 En la mayoría de los casos podrá enviar y recibir datos utilizando los métodos y propiedades de <xref:System.Net.WebRequest> ordenar.  Sin embargo, si necesita tener acceso a propiedades protocolo\- específicas, puede convertir <xref:System.Net.WebRequest> a una instancia concreta de la clase derivada.  
  
 Para aprovecharse de protocolos conectables, sus descendientes de <xref:System.Net.WebRequest> deben proporcionar una transacción predeterminada de la solicitud\-y\- respuesta que no requiere propiedades protocolo\- específicas establecer.  Por ejemplo, la clase de <xref:System.Net.HttpWebRequest> , que implementa la clase de <xref:System.Net.WebRequest> para HTTP, proporciona una solicitud de `GET` de forma predeterminada y devuelve <xref:System.Net.HttpWebResponse> que contiene la secuencia devuelta del servidor web.  
  
## Vea también  
 [Derivar de WebRequest](../../../docs/framework/network-programming/deriving-from-webrequest.md)   
 [Derivar de WebResponse](../../../docs/framework/network-programming/deriving-from-webresponse.md)   
 [Programación para redes en .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Cómo: convertir una WebRequest a propiedades específicas del protocolo de acceso](../../../docs/framework/network-programming/how-to-typecast-a-webrequest-to-access-protocol-specific-properties.md)