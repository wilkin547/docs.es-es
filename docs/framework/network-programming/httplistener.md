---
title: HttpListener
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 68c69de839ccbd51de9f0bfa74be018f877f7731
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43416876"
---
# <a name="httplistener"></a><span data-ttu-id="1e032-102">HttpListener</span><span class="sxs-lookup"><span data-stu-id="1e032-102">HttpListener</span></span>
<span data-ttu-id="1e032-103">La clase <xref:System.Net.HttpListener> proporciona un agente de escucha del protocolo HTTP controlado mediante programación.</span><span class="sxs-lookup"><span data-stu-id="1e032-103">The <xref:System.Net.HttpListener> class provides a programmatically controlled HTTP protocol listener.</span></span> <span data-ttu-id="1e032-104">El agente de escucha está activo durante la vigencia del objeto <xref:System.Net.HttpListener> y se ejecuta dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1e032-104">The listener is active for the lifetime of the <xref:System.Net.HttpListener> object and runs within your application.</span></span>  
  
## <a name="httpsys"></a><span data-ttu-id="1e032-105">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="1e032-105">HTTP.SYS</span></span>  
 <span data-ttu-id="1e032-106">La clase <xref:System.Net.HttpListener> se basa en HTTP.sys, que es el agente de escucha de modo kernel que controla todo el tráfico HTTP de Windows.</span><span class="sxs-lookup"><span data-stu-id="1e032-106">The <xref:System.Net.HttpListener> class is built on top of HTTP.sys, which is the kernel mode listener that handles all HTTP traffic for Windows.</span></span> <span data-ttu-id="1e032-107">HTTP.sys proporciona administración de conexiones, limitación del ancho de banda y registro del servidor web.</span><span class="sxs-lookup"><span data-stu-id="1e032-107">HTTP.sys provides connection management, bandwidth throttling, and Web server logging.</span></span> <span data-ttu-id="1e032-108">Utilice la herramienta `HttpCfg.exe` para agregar certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="1e032-108">Use the `HttpCfg.exe` tool to add SSL certificates.</span></span> <span data-ttu-id="1e032-109">Para obtener más información, vea la documentación en la herramienta [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) en la documentación de [Servidor](https://go.microsoft.com/fwlink/?LinkID=178285).</span><span class="sxs-lookup"><span data-stu-id="1e032-109">For more information, see the documentation on the [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) tool in the [Server](https://go.microsoft.com/fwlink/?LinkID=178285) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e032-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e032-110">See Also</span></span>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [<span data-ttu-id="1e032-111">Servidor HTTP</span><span class="sxs-lookup"><span data-stu-id="1e032-111">HTTP Server</span></span>](https://go.microsoft.com/fwlink/?LinkID=178285)  
 [<span data-ttu-id="1e032-112">Mejoras de seguridad de Internet Information</span><span class="sxs-lookup"><span data-stu-id="1e032-112">Security Enhancements in Internet Information</span></span>](https://go.microsoft.com/fwlink/?LinkID=178286)  
 [<span data-ttu-id="1e032-113">Ejemplo de la aplicación host HttpListener de ASPX</span><span class="sxs-lookup"><span data-stu-id="1e032-113">HttpListener ASPX Host Application Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179560)  
 [<span data-ttu-id="1e032-114">Ejemplo de tecnología HttpListener</span><span class="sxs-lookup"><span data-stu-id="1e032-114">HttpListener Technology Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179558)  
 [<span data-ttu-id="1e032-115">Network Programming Samples (Ejemplos de programación de red)</span><span class="sxs-lookup"><span data-stu-id="1e032-115">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
