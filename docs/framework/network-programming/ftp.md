---
title: FTP
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e5dc6ee0f2c832e3274a1e58808acfdb56ae804c
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43862983"
---
# <a name="ftp"></a>FTP
.NET Framework proporciona compatibilidad completa para el protocolo FTP con las clases <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse>. Estas clases se derivan de <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse>. En la mayoría de los casos, las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> proporcionan todo lo necesario para realizar la solicitud, pero si necesita tener acceso a las características específicas de HTTP expuestas como propiedades, puede convertir estas clases en <xref:System.Net.FtpWebRequest> o <xref:System.Net.FtpWebResponse>.  
  
## <a name="examples"></a>Ejemplos  
 Para obtener más información, vea los temas siguientes: [How to: Download Files with FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md) (Cómo: Descargar archivos con FTP), [How to: Upload Files with FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md) (Cómo: Cargar archivos con FTP) y [How to: List Directory Contents with FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md) (Cómo: Mostrar el contenido del directorio con FTP).  
  
## <a name="ftp-and-proxies"></a>FTP y servidores proxy  
 Si un proxy (especificado por la propiedad <xref:System.Net.FtpWebRequest.Proxy%2A>) es un proxy HTTP, solo se admiten los comandos <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> y <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.  
  
## <a name="see-also"></a>Vea también  
 [Acceso a Internet a través de un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [Network Programming Samples (Ejemplos de programación de red)](../../../docs/framework/network-programming/network-programming-samples.md)  
 [Ejemplo de tecnología de cliente de FTP](https://go.microsoft.com/fwlink/?LinkID=179557)  
 [Ejemplo de tecnología de explorador FTP](https://go.microsoft.com/fwlink/?LinkID=179569)  
 [Usar protocolos de aplicaciones](../../../docs/framework/network-programming/using-application-protocols.md)
