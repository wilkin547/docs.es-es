---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: d341953b8e12b14e6a3fe8a477c16a1b3a4454ae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84580442"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="b2551-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="b2551-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="b2551-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="b2551-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="b2551-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2551-104">Description</span></span>  
 <span data-ttu-id="b2551-105">Se cerró un mensaje de nuevo.</span><span class="sxs-lookup"><span data-stu-id="b2551-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="b2551-106">Un mensaje debería cerrarse solo una vez.</span><span class="sxs-lookup"><span data-stu-id="b2551-106">A message should be closed only once.</span></span> <span data-ttu-id="b2551-107">Si este seguimiento se emite en código de extensión de usuario, indica que el código de extensión de usuario está cerrando un mensaje que ya se ha cerrado.</span><span class="sxs-lookup"><span data-stu-id="b2551-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="b2551-108">Si este seguimiento se emite a través del código de producto, indica que el código de extensión de usuario podría estar cerrando un mensaje antes de tiempo.</span><span class="sxs-lookup"><span data-stu-id="b2551-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2551-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2551-109">See also</span></span>

- [<span data-ttu-id="b2551-110">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="b2551-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="b2551-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="b2551-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b2551-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b2551-112">Administration and Diagnostics</span></span>](../index.md)
