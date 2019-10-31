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
ms.openlocfilehash: 5ed0075da1429c70900750f3f28e8ce36a41fb28
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134539"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="be299-102">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="be299-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="be299-103">Representa la caché global de ensamblados para su uso por parte de la tecnología de fusión.</span><span class="sxs-lookup"><span data-stu-id="be299-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be299-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="be299-104">Methods</span></span>  
  
|<span data-ttu-id="be299-105">Método</span><span class="sxs-lookup"><span data-stu-id="be299-105">Method</span></span>|<span data-ttu-id="be299-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="be299-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be299-107">CreateAssemblyCacheItem (método)</span><span class="sxs-lookup"><span data-stu-id="be299-107">CreateAssemblyCacheItem Method</span></span>](iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="be299-108">Obtiene una referencia a una nueva [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="be299-108">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="be299-109">CreateAssemblyScavenger (método)</span><span class="sxs-lookup"><span data-stu-id="be299-109">CreateAssemblyScavenger Method</span></span>](iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="be299-110">Reservado para uso interno por parte de la tecnología de fusión.</span><span class="sxs-lookup"><span data-stu-id="be299-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="be299-111">InstallAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="be299-111">InstallAssembly Method</span></span>](iassemblycache-installassembly-method.md)|<span data-ttu-id="be299-112">Instala el ensamblado especificado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="be299-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="be299-113">QueryAssemblyInfo (método)</span><span class="sxs-lookup"><span data-stu-id="be299-113">QueryAssemblyInfo Method</span></span>](iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="be299-114">Obtiene los datos solicitados sobre el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="be299-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="be299-115">UninstallAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="be299-115">UninstallAssembly Method</span></span>](iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="be299-116">Desinstala el ensamblado especificado de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="be299-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be299-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be299-117">Requirements</span></span>  
 <span data-ttu-id="be299-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be299-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be299-119">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="be299-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="be299-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be299-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be299-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="be299-121">See also</span></span>

- [<span data-ttu-id="be299-122">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="be299-122">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="be299-123">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="be299-123">Global Assembly Cache</span></span>](../../app-domains/gac.md)
