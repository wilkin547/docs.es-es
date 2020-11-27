---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: a8aa5e600789df1b64a8a3f1a6355aaae6a6cf4b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294435"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="096b2-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="096b2-102">System.ServiceModel.MessageClosedAgain</span></span>

<span data-ttu-id="096b2-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="096b2-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="096b2-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="096b2-104">Description</span></span>  

 <span data-ttu-id="096b2-105">Se cerró un mensaje de nuevo.</span><span class="sxs-lookup"><span data-stu-id="096b2-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="096b2-106">Un mensaje debería cerrarse solo una vez.</span><span class="sxs-lookup"><span data-stu-id="096b2-106">A message should be closed only once.</span></span> <span data-ttu-id="096b2-107">Si este seguimiento se emite en código de extensión de usuario, indica que el código de extensión de usuario está cerrando un mensaje que ya se ha cerrado.</span><span class="sxs-lookup"><span data-stu-id="096b2-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="096b2-108">Si este seguimiento se emite a través del código de producto, indica que el código de extensión de usuario podría estar cerrando un mensaje antes de tiempo.</span><span class="sxs-lookup"><span data-stu-id="096b2-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="096b2-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="096b2-109">See also</span></span>

- [<span data-ttu-id="096b2-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="096b2-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="096b2-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="096b2-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="096b2-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="096b2-112">Administration and Diagnostics</span></span>](../index.md)
