---
description: 'Más información sobre: System. ServiceModel. Activation. WebHostServiceCloseFailed'
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: fae41b72e2eb9aba76993081769afc42c0ec8975
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720454"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="57d51-103">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="57d51-103">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>

<span data-ttu-id="57d51-104">Sucede cuando un servicio no se puede cerrar correctamente y se anula.</span><span class="sxs-lookup"><span data-stu-id="57d51-104">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="57d51-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="57d51-105">Description</span></span>  

 <span data-ttu-id="57d51-106">Este código de error solo aparece en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="57d51-106">This error code only appears in the log file.</span></span> <span data-ttu-id="57d51-107">Suele indicar un error de programación, por ejemplo, cuando se intenta cerrar un servicio después de haber llamado ya a Abort.</span><span class="sxs-lookup"><span data-stu-id="57d51-107">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="57d51-108">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="57d51-108">Troubleshooting</span></span>  

 <span data-ttu-id="57d51-109">Compruebe el código fuente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="57d51-109">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57d51-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="57d51-110">See also</span></span>

- [<span data-ttu-id="57d51-111">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="57d51-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="57d51-112">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="57d51-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="57d51-113">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="57d51-113">Administration and Diagnostics</span></span>](../index.md)
