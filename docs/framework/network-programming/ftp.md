---
title: FTP - .NET
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
ms.openlocfilehash: d945f03077a863d9e1baa6b59fe8a908566aba5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "61642885"
---
# <a name="ftp"></a><span data-ttu-id="e5d86-102">FTP</span><span class="sxs-lookup"><span data-stu-id="e5d86-102">FTP</span></span>

<span data-ttu-id="e5d86-103">.NET Framework proporciona compatibilidad completa para el protocolo FTP con las clases <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="e5d86-103">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="e5d86-104">Estas clases se derivan de <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="e5d86-104">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="e5d86-105">En la mayoría de los casos, las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> proporcionan todo lo necesario para realizar la solicitud, pero si necesita tener acceso a las características específicas de HTTP expuestas como propiedades, puede convertir estas clases en <xref:System.Net.FtpWebRequest> o <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="e5d86-105">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>

## <a name="examples"></a><span data-ttu-id="e5d86-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e5d86-106">Examples</span></span>

<span data-ttu-id="e5d86-107">Para obtener más información, vea los temas siguientes: [How to: Download Files with FTP](how-to-download-files-with-ftp.md) (Cómo: Descargar archivos con FTP), [How to: Upload Files with FTP](how-to-upload-files-with-ftp.md) (Cómo: Cargar archivos con FTP) y [How to: List Directory Contents with FTP](how-to-list-directory-contents-with-ftp.md) (Cómo: Mostrar el contenido del directorio con FTP).</span><span class="sxs-lookup"><span data-stu-id="e5d86-107">For more information, see the following topics: [How to: Download Files with FTP](how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](how-to-list-directory-contents-with-ftp.md).</span></span>

## <a name="ftp-and-proxies"></a><span data-ttu-id="e5d86-108">FTP y servidores proxy</span><span class="sxs-lookup"><span data-stu-id="e5d86-108">FTP and proxies</span></span>

<span data-ttu-id="e5d86-109">Si un proxy (especificado por la propiedad <xref:System.Net.FtpWebRequest.Proxy%2A>) es un proxy HTTP, solo se admiten los comandos <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> y <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.</span><span class="sxs-lookup"><span data-stu-id="e5d86-109">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5d86-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5d86-110">See also</span></span>

- [<span data-ttu-id="e5d86-111">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="e5d86-111">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="e5d86-112">Ejemplos de programación de red</span><span class="sxs-lookup"><span data-stu-id="e5d86-112">Network Programming Samples</span></span>](network-programming-samples.md)
- [<span data-ttu-id="e5d86-113">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e5d86-113">Using Application Protocols</span></span>](using-application-protocols.md)
