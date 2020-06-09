---
title: Migración de aplicaciones de .NET Remoting a WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: d12583904e4a025a8de1103f0fb48f4656d6855e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598780"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="1eb95-102">Migración de aplicaciones de .NET Remoting a WCF</span><span class="sxs-lookup"><span data-stu-id="1eb95-102">Migrating .NET Remoting Applications to WCF</span></span>
<span data-ttu-id="1eb95-103">**Este tema es específico de una tecnología heredada que se conserva por compatibilidad con versiones anteriores de las aplicaciones existentes y no se recomienda para el nuevo desarrollo. Las aplicaciones distribuidas ahora deben desarrollarse mediante WCF.**</span><span class="sxs-lookup"><span data-stu-id="1eb95-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using WCF.**</span></span>  
  
 <span data-ttu-id="1eb95-104">Hay dos maneras de aprovechar WCF con las aplicaciones de .NET Remoting existentes: integración y migración.</span><span class="sxs-lookup"><span data-stu-id="1eb95-104">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="1eb95-105">La integración permite que .NET Remoting 2,0 y WCF se ejecuten en paralelo, lo que permite exponer los mismos objetos empresariales en ambas tecnologías simultáneamente sin tener que modificar el código existente de .NET Remoting 2,0.</span><span class="sxs-lookup"><span data-stu-id="1eb95-105">Integration allows you to have .NET Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .NET Remoting 2.0 code.</span></span> <span data-ttu-id="1eb95-106">La integración requiere que se ejecute en .NET Framework 2,0 o superior.</span><span class="sxs-lookup"><span data-stu-id="1eb95-106">Integration requires that you are running on .NET Framework 2.0 or greater.</span></span> <span data-ttu-id="1eb95-107">Si desea aprovechar las características de WCF y no necesita compatibilidad de conexión con sistemas de comunicación remota de 2,0, puede migrar todo el servicio a WCF.</span><span class="sxs-lookup"><span data-stu-id="1eb95-107">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="1eb95-108">La migración de .NET Remoting 2,0 a WCF requiere cambios en la interfaz del objeto remoto y sus opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="1eb95-108">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="1eb95-109">Ambos temas se tratan en [desde la comunicación remota con el Windows Communication Foundation](https://docs.microsoft.com/previous-versions/aa730857(v=vs.80)).</span><span class="sxs-lookup"><span data-stu-id="1eb95-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](https://docs.microsoft.com/previous-versions/aa730857(v=vs.80)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb95-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1eb95-110">See also</span></span>

- [<span data-ttu-id="1eb95-111">Información general conceptual</span><span class="sxs-lookup"><span data-stu-id="1eb95-111">Conceptual Overview</span></span>](../conceptual-overview.md)
