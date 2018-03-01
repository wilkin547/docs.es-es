---
title: HttpListener
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: b4b8c1e916aa9382d156a197fa15c2e72e900a1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="httplistener"></a><span data-ttu-id="d52f4-102">HttpListener</span><span class="sxs-lookup"><span data-stu-id="d52f4-102">HttpListener</span></span>
<span data-ttu-id="d52f4-103">La clase <xref:System.Net.HttpListener> proporciona un agente de escucha del protocolo HTTP controlado mediante programación.</span><span class="sxs-lookup"><span data-stu-id="d52f4-103">The <xref:System.Net.HttpListener> class provides a programmatically controlled HTTP protocol listener.</span></span> <span data-ttu-id="d52f4-104">El agente de escucha está activo durante la vigencia del objeto <xref:System.Net.HttpListener> y se ejecuta dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d52f4-104">The listener is active for the lifetime of the <xref:System.Net.HttpListener> object and runs within your application.</span></span>  
  
## <a name="httpsys"></a><span data-ttu-id="d52f4-105">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="d52f4-105">HTTP.SYS</span></span>  
 <span data-ttu-id="d52f4-106">La clase <xref:System.Net.HttpListener> se basa en HTTP.sys, que es el agente de escucha de modo kernel que controla todo el tráfico HTTP de Windows.</span><span class="sxs-lookup"><span data-stu-id="d52f4-106">The <xref:System.Net.HttpListener> class is built on top of HTTP.sys, which is the kernel mode listener that handles all HTTP traffic for Windows.</span></span> <span data-ttu-id="d52f4-107">HTTP.sys proporciona administración de conexiones, limitación del ancho de banda y registro del servidor web.</span><span class="sxs-lookup"><span data-stu-id="d52f4-107">HTTP.sys provides connection management, bandwidth throttling, and Web server logging.</span></span> <span data-ttu-id="d52f4-108">Utilice la herramienta `HttpCfg.exe` para agregar certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="d52f4-108">Use the `HttpCfg.exe` tool to add SSL certificates.</span></span> <span data-ttu-id="d52f4-109">Para obtener más información, vea la documentación en la herramienta [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) en la documentación de [Servidor](http://go.microsoft.com/fwlink/?LinkID=178285).</span><span class="sxs-lookup"><span data-stu-id="d52f4-109">For more information, see the documentation on the [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) tool in the [Server](http://go.microsoft.com/fwlink/?LinkID=178285) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d52f4-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d52f4-110">See Also</span></span>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [<span data-ttu-id="d52f4-111">Servidor HTTP</span><span class="sxs-lookup"><span data-stu-id="d52f4-111">HTTP Server</span></span>](http://go.microsoft.com/fwlink/?LinkID=178285)  
 [<span data-ttu-id="d52f4-112">Mejoras de seguridad en Internet Information</span><span class="sxs-lookup"><span data-stu-id="d52f4-112">Security Enhancements in Internet Information</span></span>](http://go.microsoft.com/fwlink/?LinkID=178286)  
 [<span data-ttu-id="d52f4-113">Ejemplo de la aplicación host HttpListener de ASPX</span><span class="sxs-lookup"><span data-stu-id="d52f4-113">HttpListener ASPX Host Application Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179560)  
 [<span data-ttu-id="d52f4-114">Ejemplo de tecnología HttpListener</span><span class="sxs-lookup"><span data-stu-id="d52f4-114">HttpListener Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179558)  
 [<span data-ttu-id="d52f4-115">Network Programming Samples (Ejemplos de programación de red)</span><span class="sxs-lookup"><span data-stu-id="d52f4-115">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
