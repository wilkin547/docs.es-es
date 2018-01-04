---
title: "Implementación de un proyecto de biblioteca de WFC"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbbbff1d88559f8ab35caa48fcb04ff1cd7bf015
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-a-wcf-library-project"></a><span data-ttu-id="f68c4-102">Implementación de un proyecto de biblioteca de WFC</span><span class="sxs-lookup"><span data-stu-id="f68c4-102">Deploying a WCF Library Project</span></span>
<span data-ttu-id="f68c4-103">En este tema se describe cómo puede implementar un proyecto de biblioteca de servicios de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f68c4-103">This topic describes how you can deploy a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Service Library Project.</span></span>  
  
## <a name="deploying-a-wcf-service-library"></a><span data-ttu-id="f68c4-104">Implementación de una biblioteca de servicios de WFC</span><span class="sxs-lookup"><span data-stu-id="f68c4-104">Deploying a WCF Service Library</span></span>  
 <span data-ttu-id="f68c4-105">Una biblioteca de servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] es una biblioteca de vínculo dinámico (DLL).</span><span class="sxs-lookup"><span data-stu-id="f68c4-105">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library is a dynamic-link library (DLL).</span></span> <span data-ttu-id="f68c4-106">Como tal, no se puede ejecutar por sí misma.</span><span class="sxs-lookup"><span data-stu-id="f68c4-106">As such, it cannot be executed on its own.</span></span> <span data-ttu-id="f68c4-107">Se ha de implementar en un entorno de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="f68c4-107">It needs to be deployed into a hosting environment.</span></span> <span data-ttu-id="f68c4-108">Para obtener más información acerca de este proceso, consulte [de hospedaje y consumo de servicios WCF](http://go.microsoft.com/fwlink/?LinkId=99932).</span><span class="sxs-lookup"><span data-stu-id="f68c4-108">For more information about this process, see [Hosting and Consuming WCF Services](http://go.microsoft.com/fwlink/?LinkId=99932).</span></span>  
  
 <span data-ttu-id="f68c4-109">Una biblioteca de servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se puede implementar como cualquier otro servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f68c4-109">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library can be deployed like any other [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="f68c4-110">Sin embargo, tenga en cuenta que [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] no admite la configuración de los archivos DLL.</span><span class="sxs-lookup"><span data-stu-id="f68c4-110">However, be aware that [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] does not support configuration for DLLs.</span></span> <span data-ttu-id="f68c4-111"><xref:System.Configuration> admite un archivo de configuración por dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f68c4-111"><xref:System.Configuration> supports one configuration file per app-domain.</span></span> <span data-ttu-id="f68c4-112">El proyecto de biblioteca de servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] palia esta limitación proporcionando un archivo App.config para la biblioteca durante el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="f68c4-112">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library project alleviates this limitation by providing an App.config file for the library during development.</span></span> <span data-ttu-id="f68c4-113">Sin embargo, el archivo App.config no se reconoce después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="f68c4-113">However, the App.config file is not recognized after deployment.</span></span>  
  
 <span data-ttu-id="f68c4-114">Tiene que pasar su código de configuración al archivo de configuración reconocido por su entorno de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="f68c4-114">You have to move your configuration code into the configuration file recognized by your hosting environment.</span></span> <span data-ttu-id="f68c4-115">Para el autohospedaje, debería copiar el contenido del archivo App.config en el archivo App.config del hospedaje ejecutable.</span><span class="sxs-lookup"><span data-stu-id="f68c4-115">For self-hosting, you should copy the contents of the App.config file into the App.config file of the hosting executable.</span></span> <span data-ttu-id="f68c4-116">Si utiliza IIS para hospedar su servicio, debería copiar el contenido del archivo App.config en el archivo Web.config del directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="f68c4-116">If you use IIS to host your service, you should copy the contents of the App.config file into the Web.config file of the virtual directory.</span></span>
