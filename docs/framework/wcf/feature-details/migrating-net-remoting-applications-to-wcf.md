---
title: Migración de aplicaciones de .NET Remoting a WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 4040fb0ac223f91705a49b733f6a1f42d144068e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091130"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="d3bf6-102">Migración de aplicaciones de .NET Remoting a WCF</span><span class="sxs-lookup"><span data-stu-id="d3bf6-102">Migrating .NET Remoting Applications to WCF</span></span>
**<span data-ttu-id="d3bf6-103">Este tema es específico de una tecnología heredada que se mantiene para la compatibilidad con versiones anteriores con aplicaciones existentes y no se recomienda para nuevo desarrollo.</span><span class="sxs-lookup"><span data-stu-id="d3bf6-103">This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development.</span></span> <span data-ttu-id="d3bf6-104">Las aplicaciones distribuidas se deberían desarrollar con WCF.</span><span class="sxs-lookup"><span data-stu-id="d3bf6-104">Distributed applications should now be developed using WCF.</span></span>**  
  
 <span data-ttu-id="d3bf6-105">Hay dos maneras de sacar partido de WCF con las aplicaciones de .NET Remoting existentes: integración y migración.</span><span class="sxs-lookup"><span data-stu-id="d3bf6-105">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="d3bf6-106">Integración le permite tener .NET Remoting 2.0 y WCF está ejecutando en paralelo, lo que le permite exponer los mismos objetos de negocio sobre ambas tecnologías al mismo tiempo sin tener que modificar el código de .NET Remoting 2.0 existente.</span><span class="sxs-lookup"><span data-stu-id="d3bf6-106">Integration allows you to have .NET Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .NET Remoting 2.0 code.</span></span> <span data-ttu-id="d3bf6-107">La integración requiere que trabaje con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="d3bf6-107">Integration requires that you are running on [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 or greater.</span></span> <span data-ttu-id="d3bf6-108">Si desea aprovechar las características WCF y no necesita compatibilidad de conexión con sistemas de comunicación remota 2.0, puede migrar su servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="d3bf6-108">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="d3bf6-109">Migración de la versión 2.0 de .NET Remoting a WCF requiere cambios en la interfaz del objeto remoto y su configuración.</span><span class="sxs-lookup"><span data-stu-id="d3bf6-109">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="d3bf6-110">Ambos de estos temas se tratan en [de Remoting a Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).</span><span class="sxs-lookup"><span data-stu-id="d3bf6-110">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3bf6-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3bf6-111">See also</span></span>

- [<span data-ttu-id="d3bf6-112">Información conceptual</span><span class="sxs-lookup"><span data-stu-id="d3bf6-112">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
