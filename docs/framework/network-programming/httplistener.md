---
title: HttpListener
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
ms.openlocfilehash: 902225085ccaceb9d90d0c25d9369ef65ae2730b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50193115"
---
# <a name="httplistener"></a><span data-ttu-id="60262-102">HttpListener</span><span class="sxs-lookup"><span data-stu-id="60262-102">HttpListener</span></span>
<span data-ttu-id="60262-103">La clase <xref:System.Net.HttpListener> proporciona un agente de escucha del protocolo HTTP controlado mediante programación.</span><span class="sxs-lookup"><span data-stu-id="60262-103">The <xref:System.Net.HttpListener> class provides a programmatically controlled HTTP protocol listener.</span></span> <span data-ttu-id="60262-104">El agente de escucha está activo durante la vigencia del objeto <xref:System.Net.HttpListener> y se ejecuta dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="60262-104">The listener is active for the lifetime of the <xref:System.Net.HttpListener> object and runs within your application.</span></span>  
  
## <a name="httpsys"></a><span data-ttu-id="60262-105">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="60262-105">HTTP.SYS</span></span>  
 <span data-ttu-id="60262-106">La clase <xref:System.Net.HttpListener> se basa en HTTP.sys, que es el agente de escucha de modo kernel que controla todo el tráfico HTTP de Windows.</span><span class="sxs-lookup"><span data-stu-id="60262-106">The <xref:System.Net.HttpListener> class is built on top of HTTP.sys, which is the kernel mode listener that handles all HTTP traffic for Windows.</span></span> <span data-ttu-id="60262-107">HTTP.sys proporciona administración de conexiones, limitación del ancho de banda y registro del servidor web.</span><span class="sxs-lookup"><span data-stu-id="60262-107">HTTP.sys provides connection management, bandwidth throttling, and Web server logging.</span></span> <span data-ttu-id="60262-108">Utilice la herramienta `HttpCfg.exe` para agregar certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="60262-108">Use the `HttpCfg.exe` tool to add SSL certificates.</span></span> <span data-ttu-id="60262-109">Para obtener más información, vea la documentación en la herramienta [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) en la documentación de [Servidor](https://go.microsoft.com/fwlink/?LinkID=178285).</span><span class="sxs-lookup"><span data-stu-id="60262-109">For more information, see the documentation on the [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) tool in the [Server](https://go.microsoft.com/fwlink/?LinkID=178285) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60262-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="60262-110">See Also</span></span>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [<span data-ttu-id="60262-111">Servidor HTTP</span><span class="sxs-lookup"><span data-stu-id="60262-111">HTTP Server</span></span>](https://go.microsoft.com/fwlink/?LinkID=178285)  
 [<span data-ttu-id="60262-112">Mejoras de seguridad de Internet Information</span><span class="sxs-lookup"><span data-stu-id="60262-112">Security Enhancements in Internet Information</span></span>](https://go.microsoft.com/fwlink/?LinkID=178286)  
 [<span data-ttu-id="60262-113">Ejemplo de la aplicación host HttpListener de ASPX</span><span class="sxs-lookup"><span data-stu-id="60262-113">HttpListener ASPX Host Application Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179560)  
 [<span data-ttu-id="60262-114">Ejemplo de tecnología HttpListener</span><span class="sxs-lookup"><span data-stu-id="60262-114">HttpListener Technology Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179558)  
 [<span data-ttu-id="60262-115">Network Programming Samples (Ejemplos de programación de red)</span><span class="sxs-lookup"><span data-stu-id="60262-115">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
