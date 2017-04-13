---
title: "FTP | Microsoft Docs"
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
  - "FTP"
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# FTP
.NET Framework proporciona compatibilidad completa para el protocolo FTP con las clases de <xref:System.Net.FtpWebRequest> y de <xref:System.Net.FtpWebResponse> .  Estas clases se derivan de <xref:System.Net.WebRequest> y de <xref:System.Net.WebResponse>.  En la mayoría de los casos, <xref:System.Net.WebRequest> y las clases de <xref:System.Net.WebResponse> proporcionan todo que sea necesario realizar la solicitud, pero si necesita obtener acceso a las características FTP\- específicas expuestas como propiedades, puede convertir estas clases a <xref:System.Net.FtpWebRequest> o a <xref:System.Net.FtpWebResponse>.  
  
## Ejemplos  
 Para obtener más información, vea los temas siguientes: [Cómo: descargar archivos mediante FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [Cómo: cargar archivos con FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md), y [Cómo: enumerar los contenidos del directorio con FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).  
  
## FTP y servidores proxy  
 Si un proxy \(especificado por la propiedad de <xref:System.Net.FtpWebRequest.Proxy%2A> \) es un proxy HTTP, sólo admiten <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, y comandos de <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> .  
  
## Vea también  
 [Acceso a Internet a través de un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [Ejemplos de programación de red](../../../docs/framework/network-programming/network-programming-samples.md)   
 [Ejemplo de tecnología de cliente FTP](http://go.microsoft.com/fwlink/?LinkID=179557)   
 [Explorador Technology Sample FTP](http://go.microsoft.com/fwlink/?LinkID=179569)   
 [Usar protocolos de aplicaciones](../../../docs/framework/network-programming/using-application-protocols.md)