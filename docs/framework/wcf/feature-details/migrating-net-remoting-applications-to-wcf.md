---
title: "Migración de aplicaciones de .NET Remoting a WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b7d305adf1810832016cdafbb60fc025f17e0786
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="e2bcb-102">Migración de aplicaciones de .NET Remoting a WCF</span><span class="sxs-lookup"><span data-stu-id="e2bcb-102">Migrating .NET Remoting Applications to WCF</span></span>
<span data-ttu-id="e2bcb-103">**Este tema es específico de una tecnología heredada que se mantiene para la compatibilidad con versiones anteriores con aplicaciones existentes y no se recomienda para nuevo desarrollo. Las aplicaciones distribuidas se deberían desarrollar usando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].**</span><span class="sxs-lookup"><span data-stu-id="e2bcb-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].**</span></span>  
  
 <span data-ttu-id="e2bcb-104">Hay dos maneras de sacar provecho de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con aplicaciones .NET Remoting existentes: la integración y la migración.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-104">There are two ways to take advantage of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="e2bcb-105">La integración le permite tener .Net Remoting 2.0 e [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ejecutándose lado a lado, permitiéndole exponer los mismos objetos de negocio sobre ambas tecnologías de manera simultánea sin tener que modificar su código existente de .NET Remoting 2.0.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-105">Integration allows you to have .Net Remoting 2.0 and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .Net Remoting 2.0 code.</span></span> <span data-ttu-id="e2bcb-106">La integración requiere que trabaje con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-106">Integration requires that you are running on [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 or greater.</span></span> <span data-ttu-id="e2bcb-107">Si desea aprovecharse de las características de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y no necesita la compatibilidad de la conexión con sistemas de comunicación remota 2.0, puede migrar su servicio a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2bcb-107">If you want to take advantage of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="e2bcb-108">La migración de .NET Remoting 2.0 a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requiere la realización de cambios en la interfaz del objeto remoto y su configuración.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-108">Migration from .NET Remoting 2.0 to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="e2bcb-109">En estos temas se explican en [de comunicación remota de Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).</span><span class="sxs-lookup"><span data-stu-id="e2bcb-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2bcb-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2bcb-110">See Also</span></span>  
 [<span data-ttu-id="e2bcb-111">Información conceptual</span><span class="sxs-lookup"><span data-stu-id="e2bcb-111">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
