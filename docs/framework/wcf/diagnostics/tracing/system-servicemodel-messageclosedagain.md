---
title: System.ServiceModel.MessageClosedAgain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f3963fe28ccaf55b3946254e395b770619c8f22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="433b5-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="433b5-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="433b5-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="433b5-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="433b5-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="433b5-104">Description</span></span>  
 <span data-ttu-id="433b5-105">Se cerró un mensaje de nuevo.</span><span class="sxs-lookup"><span data-stu-id="433b5-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="433b5-106">Un mensaje debería cerrarse solo una vez.</span><span class="sxs-lookup"><span data-stu-id="433b5-106">A message should be closed only once.</span></span> <span data-ttu-id="433b5-107">Si este seguimiento se emite en código de extensión de usuario, indica que el código de extensión de usuario está cerrando un mensaje que ya se ha cerrado.</span><span class="sxs-lookup"><span data-stu-id="433b5-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="433b5-108">Si este seguimiento se emite a través del código de producto, indica que el código de extensión de usuario podría estar cerrando un mensaje antes de tiempo.</span><span class="sxs-lookup"><span data-stu-id="433b5-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="433b5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="433b5-109">See Also</span></span>  
 [<span data-ttu-id="433b5-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="433b5-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="433b5-111">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="433b5-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="433b5-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="433b5-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
