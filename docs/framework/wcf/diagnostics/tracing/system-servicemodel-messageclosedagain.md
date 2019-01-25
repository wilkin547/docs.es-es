---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: bcac4683655476c6aa868232b0483336b815b6cc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705987"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="ecfa3-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="ecfa3-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="ecfa3-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="ecfa3-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="ecfa3-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecfa3-104">Description</span></span>  
 <span data-ttu-id="ecfa3-105">Se cerró un mensaje de nuevo.</span><span class="sxs-lookup"><span data-stu-id="ecfa3-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="ecfa3-106">Un mensaje debería cerrarse solo una vez.</span><span class="sxs-lookup"><span data-stu-id="ecfa3-106">A message should be closed only once.</span></span> <span data-ttu-id="ecfa3-107">Si este seguimiento se emite en código de extensión de usuario, indica que el código de extensión de usuario está cerrando un mensaje que ya se ha cerrado.</span><span class="sxs-lookup"><span data-stu-id="ecfa3-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="ecfa3-108">Si este seguimiento se emite a través del código de producto, indica que el código de extensión de usuario podría estar cerrando un mensaje antes de tiempo.</span><span class="sxs-lookup"><span data-stu-id="ecfa3-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecfa3-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecfa3-109">See also</span></span>
- [<span data-ttu-id="ecfa3-110">Traza</span><span class="sxs-lookup"><span data-stu-id="ecfa3-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="ecfa3-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="ecfa3-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ecfa3-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ecfa3-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
