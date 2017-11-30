---
title: Interfaces de hospedaje
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a3cad92c204fa10f72d7a9a61460f1234206cb39
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-interfaces"></a><span data-ttu-id="5f5f7-102">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="5f5f7-102">Hosting Interfaces</span></span>
<span data-ttu-id="5f5f7-103">Esta sección describen las interfaces que no administrada de hosts pueden usar para integrar common language runtime (CLR) en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5f5f7-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="5f5f7-104">Las interfaces de hospedaje de .NET Framework versión 2.0 sustituyen a las interfaces de la versión 1.0 y 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5f5f7-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="5f5f7-105">Hay diferencias significativas entre los dos conjuntos de interfaces.</span><span class="sxs-lookup"><span data-stu-id="5f5f7-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="5f5f7-106">Combinación de ellos puede provocar un comportamiento inesperado y no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="5f5f7-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="5f5f7-107">Las versiones de .NET Framework 3.0 y 3.5 usan las interfaces de hospedaje de .NET Framework versión 2.0 y no introducen las características de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="5f5f7-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="5f5f7-108">El [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] interfaces de hospedaje sustituyen a las interfaces de .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="5f5f7-108">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="5f5f7-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5f5f7-109">In This Section</span></span>  
 [<span data-ttu-id="5f5f7-110">Coclases e Interfaces de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="5f5f7-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="5f5f7-111">Describe las interfaces de hospedaje presentadas en las versiones 1.0 y 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5f5f7-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="5f5f7-112">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="5f5f7-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="5f5f7-113">Describe las interfaces de hospedaje presentadas en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5f5f7-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="5f5f7-114">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="5f5f7-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="5f5f7-115">Describe las interfaces de hospedaje presentadas en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f5f7-115">Describes the hosting interfaces introduced in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5f5f7-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="5f5f7-116">Related Sections</span></span>  
 [<span data-ttu-id="5f5f7-117">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="5f5f7-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="5f5f7-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="5f5f7-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="5f5f7-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="5f5f7-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="5f5f7-120">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="5f5f7-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="5f5f7-121">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="5f5f7-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 [<span data-ttu-id="5f5f7-122">Hosts en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5f5f7-122">Runtime Hosts</span></span>](http://msdn.microsoft.com/en-us/99d9246a-b994-4fe5-985c-8588d1d59998)
