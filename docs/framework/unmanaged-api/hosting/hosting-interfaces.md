---
title: Interfaces de hospedaje
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e330e0d06077d1eef63cf44f31bbcbf7c3431b59
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303314"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="c6c61-102">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c6c61-102">Hosting Interfaces</span></span>
<span data-ttu-id="c6c61-103">Esta sección describen las interfaces que no administrada de hosts pueden usar para integrar common language runtime (CLR) en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c6c61-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="c6c61-104">Las interfaces de hospedaje de .NET Framework versión 2.0 sustituyen a las interfaces de la versión 1.0 y 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c6c61-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="c6c61-105">Hay diferencias significativas entre los dos conjuntos de interfaces.</span><span class="sxs-lookup"><span data-stu-id="c6c61-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="c6c61-106">Combinación de ellos podría provocar un comportamiento inesperado y no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="c6c61-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="c6c61-107">Las versiones de .NET Framework 3.0 y 3.5 usan las interfaces de hospedaje de .NET Framework versión 2.0 y no presentan las características de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="c6c61-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="c6c61-108">El [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] interfaces de hospedaje sustituyen a las interfaces de .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="c6c61-108">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="c6c61-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c6c61-109">In This Section</span></span>  
 [<span data-ttu-id="c6c61-110">Coclases e interfaces de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="c6c61-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="c6c61-111">Describe las interfaces de hospedaje que se introdujeron en las versiones 1.0 y 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c6c61-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="c6c61-112">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="c6c61-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="c6c61-113">Describe las interfaces de hospedaje que se introdujo en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c6c61-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="c6c61-114">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="c6c61-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="c6c61-115">Describe las interfaces de hospedaje presentadas en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6c61-115">Describes the hosting interfaces introduced in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c6c61-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c6c61-116">Related Sections</span></span>  
 [<span data-ttu-id="c6c61-117">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="c6c61-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="c6c61-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="c6c61-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="c6c61-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="c6c61-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="c6c61-120">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c6c61-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="c6c61-121">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="c6c61-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 <span data-ttu-id="c6c61-122">[Hosts de runtime](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c6c61-122">[Runtime Hosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
