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
# <a name="ftp"></a><span data-ttu-id="f72f2-102">FTP</span><span class="sxs-lookup"><span data-stu-id="f72f2-102">FTP</span></span>
<span data-ttu-id="f72f2-103">.NET Framework proporciona compatibilidad completa para el protocolo FTP con las clases <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="f72f2-103">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="f72f2-104">Estas clases se derivan de <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="f72f2-104">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="f72f2-105">En la mayoría de los casos, las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> proporcionan todo lo necesario para realizar la solicitud, pero si necesita tener acceso a las características específicas de HTTP expuestas como propiedades, puede convertir estas clases en <xref:System.Net.FtpWebRequest> o <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="f72f2-105">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f72f2-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f72f2-106">Examples</span></span>  
 <span data-ttu-id="f72f2-107">Para obtener más información, vea los temas siguientes: [How to: Download Files with FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md) (Cómo: Descargar archivos con FTP), [How to: Upload Files with FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md) (Cómo: Cargar archivos con FTP) y [How to: List Directory Contents with FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md) (Cómo: Mostrar el contenido del directorio con FTP).</span><span class="sxs-lookup"><span data-stu-id="f72f2-107">For more information, see the following topics: [How to: Download Files with FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).</span></span>  
  
## <a name="ftp-and-proxies"></a><span data-ttu-id="f72f2-108">FTP y servidores proxy</span><span class="sxs-lookup"><span data-stu-id="f72f2-108">FTP and proxies</span></span>  
 <span data-ttu-id="f72f2-109">Si un proxy (especificado por la propiedad <xref:System.Net.FtpWebRequest.Proxy%2A>) es un proxy HTTP, solo se admiten los comandos <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> y <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.</span><span class="sxs-lookup"><span data-stu-id="f72f2-109">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72f2-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f72f2-110">See Also</span></span>  
 [<span data-ttu-id="f72f2-111">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="f72f2-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="f72f2-112">Network Programming Samples (Ejemplos de programación de red)</span><span class="sxs-lookup"><span data-stu-id="f72f2-112">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)  
 [<span data-ttu-id="f72f2-113">Ejemplo de tecnología de cliente de FTP</span><span class="sxs-lookup"><span data-stu-id="f72f2-113">FTP Client Technology Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179557)  
 [<span data-ttu-id="f72f2-114">Ejemplo de tecnología de explorador FTP</span><span class="sxs-lookup"><span data-stu-id="f72f2-114">FTP Explorer Technology Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179569)  
 [<span data-ttu-id="f72f2-115">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f72f2-115">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
