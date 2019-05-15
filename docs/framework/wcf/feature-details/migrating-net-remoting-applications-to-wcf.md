---
title: Migración de aplicaciones de .NET Remoting a WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: c0ce7c9badc8bad6eedc58827b6efe2595ab2cf8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592869"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="2450a-102">Migración de aplicaciones de .NET Remoting a WCF</span><span class="sxs-lookup"><span data-stu-id="2450a-102">Migrating .NET Remoting Applications to WCF</span></span>
<span data-ttu-id="2450a-103">**Este tema es específico de una tecnología heredada que se mantiene para la compatibilidad con versiones anteriores con aplicaciones existentes y no se recomienda para nuevo desarrollo. Las aplicaciones distribuidas se deberían desarrollar con WCF.**</span><span class="sxs-lookup"><span data-stu-id="2450a-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using WCF.**</span></span>  
  
 <span data-ttu-id="2450a-104">Hay dos maneras de sacar partido de WCF con las aplicaciones de .NET Remoting existentes: integración y migración.</span><span class="sxs-lookup"><span data-stu-id="2450a-104">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="2450a-105">Integración le permite tener .NET Remoting 2.0 y WCF está ejecutando en paralelo, lo que le permite exponer los mismos objetos de negocio sobre ambas tecnologías al mismo tiempo sin tener que modificar el código de .NET Remoting 2.0 existente.</span><span class="sxs-lookup"><span data-stu-id="2450a-105">Integration allows you to have .NET Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .NET Remoting 2.0 code.</span></span> <span data-ttu-id="2450a-106">Integración requiere que se está ejecutando en .NET Framework 2.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="2450a-106">Integration requires that you are running on .NET Framework 2.0 or greater.</span></span> <span data-ttu-id="2450a-107">Si desea aprovechar las características WCF y no necesita compatibilidad de conexión con sistemas de comunicación remota 2.0, puede migrar su servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="2450a-107">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="2450a-108">Migración de la versión 2.0 de .NET Remoting a WCF requiere cambios en la interfaz del objeto remoto y su configuración.</span><span class="sxs-lookup"><span data-stu-id="2450a-108">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="2450a-109">Ambos de estos temas se tratan en [de Remoting a Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).</span><span class="sxs-lookup"><span data-stu-id="2450a-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2450a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2450a-110">See also</span></span>

- [<span data-ttu-id="2450a-111">Información conceptual</span><span class="sxs-lookup"><span data-stu-id="2450a-111">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
