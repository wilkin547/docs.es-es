---
title: "PNRP en el desarrollo de aplicaciones | Microsoft Docs"
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
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# PNRP en el desarrollo de aplicaciones
En Windows Vista, las aplicaciones de red pueden tener acceso a la publicación de nombre y resolución funciona a través de una interfaz de programación de aplicaciones simplificada de PNRP \(API\).  
  
## Implementar en Peer Name Resolution Protocol  
 Con el PNRP simplificado API, las nubes no se especifican explícitamente para registrar el nombre y dirección; el componente de PNRP determina automáticamente las nubes adecuadas para combinar y instrucciones para publicar en las nubes.  
  
 Para la resolución de nombres muy simplificada de PNRP en Windows Vista, los nombres de PNRP ahora se integran en la función de Windows Sockets de getaddrinfo \(\).  Para utilizar PNRP para resolver un nombre a una dirección IPv6, las aplicaciones pueden utilizar la función de getaddrinfo \(\) para resolver el nombre de dominio completo \(FQDN\) name.prnp.  red, donde name es el nombre del mismo nivel que se resuelve.  El pnrp.  el dominio neto es un dominio reservado en Windows Vista para la resolución de nombres de PNRP.  
  
 El paso de mensajes entre las aplicaciones de PeerToPeer todavía controla arquitecturas subyacentes como PeerChannel y WCF [datos grandes y Streaming](http://go.microsoft.com/fwlink/?LinkID=179652).  
  
## Vea también  
 <xref:System.Net.PeerToPeer>