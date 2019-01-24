---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 157cc9f5f520f376c0c055ab49b116bc7961f421
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641075"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="09f42-102">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09f42-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="09f42-103">Representa la caché global de ensamblados para su uso por la tecnología fusion.</span><span class="sxs-lookup"><span data-stu-id="09f42-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="09f42-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="09f42-104">Methods</span></span>  
  
|<span data-ttu-id="09f42-105">Método</span><span class="sxs-lookup"><span data-stu-id="09f42-105">Method</span></span>|<span data-ttu-id="09f42-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="09f42-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="09f42-107">CreateAssemblyCacheItem (método)</span><span class="sxs-lookup"><span data-stu-id="09f42-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="09f42-108">Obtiene una referencia a un nuevo [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="09f42-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="09f42-109">CreateAssemblyScavenger (método)</span><span class="sxs-lookup"><span data-stu-id="09f42-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="09f42-110">Reservado para uso interno por la tecnología fusion.</span><span class="sxs-lookup"><span data-stu-id="09f42-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="09f42-111">InstallAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="09f42-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="09f42-112">Instala al ensamblado especificado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="09f42-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="09f42-113">QueryAssemblyInfo (método)</span><span class="sxs-lookup"><span data-stu-id="09f42-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="09f42-114">Obtiene los datos solicitados sobre el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="09f42-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="09f42-115">UninstallAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="09f42-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="09f42-116">Desinstala el ensamblado especificado de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="09f42-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09f42-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09f42-117">Requirements</span></span>  
 <span data-ttu-id="09f42-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09f42-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09f42-119">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="09f42-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="09f42-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09f42-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09f42-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="09f42-121">See also</span></span>
- [<span data-ttu-id="09f42-122">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="09f42-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="09f42-123">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="09f42-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
