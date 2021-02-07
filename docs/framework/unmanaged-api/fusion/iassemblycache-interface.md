---
description: 'Más información acerca de: interfaz IAssemblyCache'
title: IAssemblyCache (Interfaz)
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
ms.openlocfilehash: 29c042fc101180085a697e02376b91b0e1ffd19f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760932"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="5a42b-103">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a42b-103">IAssemblyCache Interface</span></span>

<span data-ttu-id="5a42b-104">Representa la caché global de ensamblados para su uso por parte de la tecnología de fusión.</span><span class="sxs-lookup"><span data-stu-id="5a42b-104">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a42b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5a42b-105">Methods</span></span>  
  
|<span data-ttu-id="5a42b-106">Método</span><span class="sxs-lookup"><span data-stu-id="5a42b-106">Method</span></span>|<span data-ttu-id="5a42b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a42b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a42b-108">Método CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="5a42b-108">CreateAssemblyCacheItem Method</span></span>](iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="5a42b-109">Obtiene una referencia a una nueva [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5a42b-109">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="5a42b-110">Método CreateAssemblyScavenger</span><span class="sxs-lookup"><span data-stu-id="5a42b-110">CreateAssemblyScavenger Method</span></span>](iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="5a42b-111">Reservado para uso interno por parte de la tecnología de fusión.</span><span class="sxs-lookup"><span data-stu-id="5a42b-111">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="5a42b-112">Método InstallAssembly</span><span class="sxs-lookup"><span data-stu-id="5a42b-112">InstallAssembly Method</span></span>](iassemblycache-installassembly-method.md)|<span data-ttu-id="5a42b-113">Instala el ensamblado especificado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5a42b-113">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="5a42b-114">Método QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="5a42b-114">QueryAssemblyInfo Method</span></span>](iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="5a42b-115">Obtiene los datos solicitados sobre el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="5a42b-115">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="5a42b-116">Método UninstallAssembly</span><span class="sxs-lookup"><span data-stu-id="5a42b-116">UninstallAssembly Method</span></span>](iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="5a42b-117">Desinstala el ensamblado especificado de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5a42b-117">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a42b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a42b-118">Requirements</span></span>  

 <span data-ttu-id="5a42b-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a42b-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a42b-120">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5a42b-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5a42b-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a42b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a42b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a42b-122">See also</span></span>

- [<span data-ttu-id="5a42b-123">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="5a42b-123">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="5a42b-124">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="5a42b-124">Global Assembly Cache</span></span>](../../app-domains/gac.md)
