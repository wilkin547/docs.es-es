---
description: Más información acerca de cómo migrar aplicaciones de .NET Remoting a WCF
title: Migración de aplicaciones de .NET Remoting a WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 551ad759c11ab24d6ab83a466e8e94b8226bf4d4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733767"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="e36db-103">Migración de aplicaciones de .NET Remoting a WCF</span><span class="sxs-lookup"><span data-stu-id="e36db-103">Migrating .NET Remoting Applications to WCF</span></span>

<span data-ttu-id="e36db-104">**Este tema es específico de una tecnología heredada que se conserva por compatibilidad con versiones anteriores de las aplicaciones existentes y no se recomienda para el nuevo desarrollo. Las aplicaciones distribuidas ahora deben desarrollarse mediante WCF.**</span><span class="sxs-lookup"><span data-stu-id="e36db-104">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using WCF.**</span></span>  
  
 <span data-ttu-id="e36db-105">Hay dos maneras de aprovechar WCF con las aplicaciones de .NET Remoting existentes: integración y migración.</span><span class="sxs-lookup"><span data-stu-id="e36db-105">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="e36db-106">La integración permite que .NET Remoting 2,0 y WCF se ejecuten en paralelo, lo que permite exponer los mismos objetos empresariales en ambas tecnologías simultáneamente sin tener que modificar el código existente de .NET Remoting 2,0.</span><span class="sxs-lookup"><span data-stu-id="e36db-106">Integration allows you to have .NET Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .NET Remoting 2.0 code.</span></span> <span data-ttu-id="e36db-107">La integración requiere que se ejecute en .NET Framework 2,0 o superior.</span><span class="sxs-lookup"><span data-stu-id="e36db-107">Integration requires that you are running on .NET Framework 2.0 or greater.</span></span> <span data-ttu-id="e36db-108">Si desea aprovechar las características de WCF y no necesita compatibilidad de conexión con sistemas de comunicación remota de 2,0, puede migrar todo el servicio a WCF.</span><span class="sxs-lookup"><span data-stu-id="e36db-108">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="e36db-109">La migración de .NET Remoting 2,0 a WCF requiere cambios en la interfaz del objeto remoto y sus opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="e36db-109">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="e36db-110">Ambos temas se tratan en [desde la comunicación remota con el Windows Communication Foundation](/previous-versions/aa730857(v=vs.80)).</span><span class="sxs-lookup"><span data-stu-id="e36db-110">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](/previous-versions/aa730857(v=vs.80)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e36db-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e36db-111">See also</span></span>

- [<span data-ttu-id="e36db-112">Información general conceptual</span><span class="sxs-lookup"><span data-stu-id="e36db-112">Conceptual Overview</span></span>](../conceptual-overview.md)
