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
ms.openlocfilehash: 4302a73f9f077c2e1bf4f66c2b80ab025ae4a62c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430588"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="502aa-102">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="502aa-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="502aa-103">Representa la caché global de ensamblados para su uso por la tecnología de fusión.</span><span class="sxs-lookup"><span data-stu-id="502aa-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="502aa-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="502aa-104">Methods</span></span>  
  
|<span data-ttu-id="502aa-105">Método</span><span class="sxs-lookup"><span data-stu-id="502aa-105">Method</span></span>|<span data-ttu-id="502aa-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="502aa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="502aa-107">CreateAssemblyCacheItem (método)</span><span class="sxs-lookup"><span data-stu-id="502aa-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="502aa-108">Obtiene una referencia a una nueva [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="502aa-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="502aa-109">CreateAssemblyScavenger (método)</span><span class="sxs-lookup"><span data-stu-id="502aa-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="502aa-110">Reservado para uso interno por la tecnología fusion.</span><span class="sxs-lookup"><span data-stu-id="502aa-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="502aa-111">InstallAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="502aa-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="502aa-112">Instala al ensamblado especificado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="502aa-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="502aa-113">QueryAssemblyInfo (método)</span><span class="sxs-lookup"><span data-stu-id="502aa-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="502aa-114">Obtiene los datos solicitados sobre el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="502aa-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="502aa-115">UninstallAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="502aa-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="502aa-116">Desinstala el ensamblado especificado de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="502aa-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="502aa-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="502aa-117">Requirements</span></span>  
 <span data-ttu-id="502aa-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="502aa-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="502aa-119">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="502aa-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="502aa-120">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="502aa-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="502aa-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="502aa-121">See Also</span></span>  
 [<span data-ttu-id="502aa-122">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="502aa-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="502aa-123">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="502aa-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
