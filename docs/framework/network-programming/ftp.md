---
title: FTP - .NET
description: Obtenga información sobre la compatibilidad total con el protocolo FTP que proporciona .NET Framework mediante el uso de las clases FtpWebRequest y FtpWebResponse.
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
ms.openlocfilehash: d21ca43cd1041df358dc5e2add9560fb33e85d83
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502592"
---
# <a name="ftp"></a>FTP

.NET Framework proporciona compatibilidad completa para el protocolo FTP con las clases <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse>. Estas clases se derivan de <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse>. En la mayoría de los casos, las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> proporcionan todo lo necesario para realizar la solicitud, pero si necesita tener acceso a las características específicas de HTTP expuestas como propiedades, puede convertir estas clases en <xref:System.Net.FtpWebRequest> o <xref:System.Net.FtpWebResponse>.

## <a name="examples"></a>Ejemplos

Para obtener más información, vea los temas siguientes: [Cómo: Descarga de archivos mediante FTP](how-to-download-files-with-ftp.md), [Cómo: Carga de archivos mediante FTP](how-to-upload-files-with-ftp.md) y [Cómo: Enumeración de los contenidos del directorio con FTP](how-to-list-directory-contents-with-ftp.md).

## <a name="ftp-and-proxies"></a>FTP y servidores proxy

Si un proxy (especificado por la propiedad <xref:System.Net.FtpWebRequest.Proxy%2A>) es un proxy HTTP, solo se admiten los comandos <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> y <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.

## <a name="see-also"></a>Vea también

- [Acceso a Internet a través de un proxy](accessing-the-internet-through-a-proxy.md)
- [Network Programming Samples (Ejemplos de programación de red)](network-programming-samples.md)
- [Usar protocolos de aplicaciones](using-application-protocols.md)
