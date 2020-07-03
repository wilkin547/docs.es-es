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
# <a name="ftp"></a><span data-ttu-id="d3186-103">FTP</span><span class="sxs-lookup"><span data-stu-id="d3186-103">FTP</span></span>

<span data-ttu-id="d3186-104">.NET Framework proporciona compatibilidad completa para el protocolo FTP con las clases <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="d3186-104">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="d3186-105">Estas clases se derivan de <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="d3186-105">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="d3186-106">En la mayoría de los casos, las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> proporcionan todo lo necesario para realizar la solicitud, pero si necesita tener acceso a las características específicas de HTTP expuestas como propiedades, puede convertir estas clases en <xref:System.Net.FtpWebRequest> o <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="d3186-106">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>

## <a name="examples"></a><span data-ttu-id="d3186-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d3186-107">Examples</span></span>

<span data-ttu-id="d3186-108">Para obtener más información, vea los temas siguientes: [Cómo: Descarga de archivos mediante FTP](how-to-download-files-with-ftp.md), [Cómo: Carga de archivos mediante FTP](how-to-upload-files-with-ftp.md) y [Cómo: Enumeración de los contenidos del directorio con FTP](how-to-list-directory-contents-with-ftp.md).</span><span class="sxs-lookup"><span data-stu-id="d3186-108">For more information, see the following topics: [How to: Download Files with FTP](how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](how-to-list-directory-contents-with-ftp.md).</span></span>

## <a name="ftp-and-proxies"></a><span data-ttu-id="d3186-109">FTP y servidores proxy</span><span class="sxs-lookup"><span data-stu-id="d3186-109">FTP and proxies</span></span>

<span data-ttu-id="d3186-110">Si un proxy (especificado por la propiedad <xref:System.Net.FtpWebRequest.Proxy%2A>) es un proxy HTTP, solo se admiten los comandos <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> y <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.</span><span class="sxs-lookup"><span data-stu-id="d3186-110">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3186-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3186-111">See also</span></span>

- [<span data-ttu-id="d3186-112">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="d3186-112">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="d3186-113">Network Programming Samples (Ejemplos de programación de red)</span><span class="sxs-lookup"><span data-stu-id="d3186-113">Network Programming Samples</span></span>](network-programming-samples.md)
- [<span data-ttu-id="d3186-114">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="d3186-114">Using Application Protocols</span></span>](using-application-protocols.md)
