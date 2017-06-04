---
title: "Permisos de web y socket | Microsoft Docs"
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
  - "Redes"
  - "posiciones [.NET Framework], aceptar"
  - "sockets, permisos"
  - "red, permisos"
  - "Internet, permisos"
  - "Recursos de red"
  - "SocketPermission (clase), acerca de la clase SocketPermission"
  - "posiciones [.NET Framework], conectar"
  - "WebPermission (clase), acerca de la clase WebPermission"
  - "permisos [.NET Framework], sockets"
  - "seguridad [.NET Framework], Internet"
  - "posiciones [.NET Framework], conceder"
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Permisos de web y socket
Seguridad de Internet para las aplicaciones mediante el espacio de nombres de <xref:System.Net> proporcionada por las clases de <xref:System.Net.WebPermission> y de <xref:System.Net.SocketPermission> .  La clase de **WebPermission** controla la derecha de una aplicación de solicitar datos de un URI o de actuar un URI a internet.  La clase de **SocketPermission** controla la derecha de una aplicación de utilizar <xref:System.Net.Sockets.Socket> para aceptar datos en un puerto local o para ponerse en contacto con dispositivos remotos mediante un protocolo de transporte en otra dirección, basándose en el host, el número de puerto, y el protocolo de transporte de socket.  
  
 El tipo de permiso utilice depende del tipo de aplicación.  Las aplicaciones que utilizan <xref:System.Net.WebRequest> y sus descendientes deben utilizar la clase de **WebPermission** para administrar permisos.  Las aplicaciones que utilizan el acceso de socket\- nivel deben utilizar la clase de **SocketPermission** para administrar permisos.  
  
 **WebPermission** y **SocketPermission** definen dos permisos: acepte y conectar.  Acepte las concesiones la aplicación el derecho de responder a una conexión entrante de otra entidad.  Conectar concesiones la aplicación el derecho de iniciar una conexión a otra parte.  
  
 Para las instancias de **SocketPermission** , acepte significa que una aplicación puede aceptar las conexiones entrantes en una dirección de transporte local; conectar significa que una aplicación puede conectarse a alguna dirección de transporte remota \(o local\).  
  
 Para las instancias de **WebPermission** , acepte significa que una aplicación puede exportar el URI controlado por **WebPermission** el mundo; conectar significa que una aplicación puede obtener acceso al URI \(si es remota o local\).  
  
## Vea también  
 [Security](../../../docs/standard/security/index.md)   
 [Seguridad en la programación para redes](../../../docs/framework/network-programming/security-in-network-programming.md)