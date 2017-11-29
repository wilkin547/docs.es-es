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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8550c30f74968d4f58d9a2fd1deac69bf9d3abe7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="0db4e-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="0db4e-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="0db4e-103">Sucede cuando un servicio no se puede cerrar correctamente y se anula.</span><span class="sxs-lookup"><span data-stu-id="0db4e-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0db4e-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="0db4e-104">Description</span></span>  
 <span data-ttu-id="0db4e-105">Este código de error solo aparece en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="0db4e-105">This error code only appears in the log file.</span></span> <span data-ttu-id="0db4e-106">Suele indicar un error de programación, por ejemplo, cuando se intenta cerrar un servicio después de haber llamado ya a Abort.</span><span class="sxs-lookup"><span data-stu-id="0db4e-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="0db4e-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="0db4e-107">Troubleshooting</span></span>  
 <span data-ttu-id="0db4e-108">Compruebe el código fuente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0db4e-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0db4e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="0db4e-109">See Also</span></span>  
 [<span data-ttu-id="0db4e-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="0db4e-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="0db4e-111">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0db4e-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="0db4e-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="0db4e-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
