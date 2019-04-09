---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: a18355d55359df665d0e936ce95da34bf07aec6a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181359"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="f53f7-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="f53f7-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="f53f7-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="f53f7-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="f53f7-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="f53f7-104">Description</span></span>  
 <span data-ttu-id="f53f7-105">Se cerró un mensaje de nuevo.</span><span class="sxs-lookup"><span data-stu-id="f53f7-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="f53f7-106">Un mensaje debería cerrarse solo una vez.</span><span class="sxs-lookup"><span data-stu-id="f53f7-106">A message should be closed only once.</span></span> <span data-ttu-id="f53f7-107">Si este seguimiento se emite en código de extensión de usuario, indica que el código de extensión de usuario está cerrando un mensaje que ya se ha cerrado.</span><span class="sxs-lookup"><span data-stu-id="f53f7-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="f53f7-108">Si este seguimiento se emite a través del código de producto, indica que el código de extensión de usuario podría estar cerrando un mensaje antes de tiempo.</span><span class="sxs-lookup"><span data-stu-id="f53f7-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f53f7-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="f53f7-109">See also</span></span>

- [<span data-ttu-id="f53f7-110">Traza</span><span class="sxs-lookup"><span data-stu-id="f53f7-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="f53f7-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="f53f7-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="f53f7-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="f53f7-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
