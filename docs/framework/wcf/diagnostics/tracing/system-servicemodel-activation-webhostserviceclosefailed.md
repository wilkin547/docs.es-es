---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1761ef66bf2aedf2d4382558ba70bf1956af0f3e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="35427-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="35427-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="35427-103">Sucede cuando un servicio no se puede cerrar correctamente y se anula.</span><span class="sxs-lookup"><span data-stu-id="35427-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="35427-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="35427-104">Description</span></span>  
 <span data-ttu-id="35427-105">Este código de error solo aparece en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="35427-105">This error code only appears in the log file.</span></span> <span data-ttu-id="35427-106">Suele indicar un error de programación, por ejemplo, cuando se intenta cerrar un servicio después de haber llamado ya a Abort.</span><span class="sxs-lookup"><span data-stu-id="35427-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="35427-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="35427-107">Troubleshooting</span></span>  
 <span data-ttu-id="35427-108">Compruebe el código fuente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35427-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35427-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="35427-109">See Also</span></span>  
 [<span data-ttu-id="35427-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="35427-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="35427-111">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="35427-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="35427-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="35427-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
