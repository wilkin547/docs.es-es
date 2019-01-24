---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: 0ed3a9a1c16247f94c739a43d84d51e4750b3c2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597663"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="85f05-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="85f05-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="85f05-103">Sucede cuando un servicio no se puede cerrar correctamente y se anula.</span><span class="sxs-lookup"><span data-stu-id="85f05-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="85f05-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="85f05-104">Description</span></span>  
 <span data-ttu-id="85f05-105">Este código de error solo aparece en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="85f05-105">This error code only appears in the log file.</span></span> <span data-ttu-id="85f05-106">Suele indicar un error de programación, por ejemplo, cuando se intenta cerrar un servicio después de haber llamado ya a Abort.</span><span class="sxs-lookup"><span data-stu-id="85f05-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="85f05-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="85f05-107">Troubleshooting</span></span>  
 <span data-ttu-id="85f05-108">Compruebe el código fuente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="85f05-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85f05-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="85f05-109">See also</span></span>
- [<span data-ttu-id="85f05-110">Traza</span><span class="sxs-lookup"><span data-stu-id="85f05-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="85f05-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="85f05-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="85f05-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="85f05-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
