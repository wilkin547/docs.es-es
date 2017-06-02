---
title: "Procedimientos recomendados para las clases System.Net | Microsoft Docs"
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
  - "enviar datos, procedimientos recomendados"
  - "solicitar datos de Internet, procedimientos recomendados"
  - "clase WebRequest, procedimientos recomendados"
  - "solicitudes de datos, procedimientos recomendados"
  - "clase WebResponse, procedimientos recomendados"
  - "procedimientos recomendados, solicitudes de datos"
  - "recibir datos, procedimientos recomendados"
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Procedimientos recomendados para las clases System.Net
Las recomendaciones siguientes le ayudarán a utilizar las clases de <xref:System.Net> al mejor ventaja:  
  
-   Utilice <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> siempre que sea posible en lugar de convertir los tipos a las clases descendientes.  Las aplicaciones que utilizan **WebRequest** y **WebResponse** pueden aprovecharse de nuevos protocolos de Internet sin necesidad de código extenso cambian.  
  
-   Al escribir las aplicaciones ASP.NET que se ejecutan en un servidor con las clases de **System.Net** , suele ser mejor, desde el punto de vista de rendimiento, utilizar los métodos asincrónicos para <xref:System.Net.WebRequest.GetResponse%2A> y <xref:System.Net.WebResponse.GetResponseStream%2A>.  
  
-   El número de conexiones abrió un recurso de internet puede tener un impacto significativo en el rendimiento y rendimiento de la red.  **System.Net** utiliza dos conexiones por la aplicación para el host de forma predeterminada.  Establecer la propiedad de <xref:System.Net.ServicePoint.ConnectionLimit%2A> en <xref:System.Net.ServicePoint> para una aplicación puede aumentar este número para un host concreto.  Establecer la propiedad de <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=fullName> puede aumentar este valor predeterminado para todos los hosts.  
  
-   Al escribir protocolos, intente de socket\- nivel para utilizar [TCPClient](frlrfsystemnetsocketstcpclientclasstopic) o [UDPClient](frlrfsystemnetsocketsudpclientclasstopic) siempre que sea posible en lugar de escribir directamente a <xref:System.Net.Sockets.Socket>.  Estas dos clases de cliente encapsulan la creación TCP y de sockets UDP sin que sea necesario controlar los detalles de la conexión.  
  
-   Al tener acceso a los sitios que requieren las credenciales, utilice la clase de <xref:System.Net.CredentialCache> para crear una caché de credenciales en lugar de proporcionandolas con cada solicitud.  La clase de **CredentialCache** busca la caché para buscar la credencial adecuada para mostrar con una solicitud, aliviándole de la responsabilidad de crear y mostrar las credenciales basándose en la dirección URL.  
  
## Vea también  
 [Programación para redes en .NET Framework](../../../docs/framework/network-programming/index.md)