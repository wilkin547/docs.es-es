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
ms.openlocfilehash: 6dab5fe941fce3c23ba718906b29c80c6d257c2f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796771"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="bd29a-102">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd29a-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="bd29a-103">Representa la caché global de ensamblados para su uso por parte de la tecnología de fusión.</span><span class="sxs-lookup"><span data-stu-id="bd29a-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bd29a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="bd29a-104">Methods</span></span>  
  
|<span data-ttu-id="bd29a-105">Método</span><span class="sxs-lookup"><span data-stu-id="bd29a-105">Method</span></span>|<span data-ttu-id="bd29a-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bd29a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bd29a-107">CreateAssemblyCacheItem (método)</span><span class="sxs-lookup"><span data-stu-id="bd29a-107">CreateAssemblyCacheItem Method</span></span>](iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="bd29a-108">Obtiene una referencia a una nueva [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="bd29a-108">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="bd29a-109">CreateAssemblyScavenger (método)</span><span class="sxs-lookup"><span data-stu-id="bd29a-109">CreateAssemblyScavenger Method</span></span>](iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="bd29a-110">Reservado para uso interno por parte de la tecnología de fusión.</span><span class="sxs-lookup"><span data-stu-id="bd29a-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="bd29a-111">InstallAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="bd29a-111">InstallAssembly Method</span></span>](iassemblycache-installassembly-method.md)|<span data-ttu-id="bd29a-112">Instala el ensamblado especificado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="bd29a-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="bd29a-113">QueryAssemblyInfo (método)</span><span class="sxs-lookup"><span data-stu-id="bd29a-113">QueryAssemblyInfo Method</span></span>](iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="bd29a-114">Obtiene los datos solicitados sobre el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="bd29a-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="bd29a-115">UninstallAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="bd29a-115">UninstallAssembly Method</span></span>](iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="bd29a-116">Desinstala el ensamblado especificado de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="bd29a-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd29a-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd29a-117">Requirements</span></span>  
 <span data-ttu-id="bd29a-118">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd29a-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd29a-119">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="bd29a-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="bd29a-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd29a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd29a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd29a-121">See also</span></span>

- [<span data-ttu-id="bd29a-122">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="bd29a-122">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="bd29a-123">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="bd29a-123">Global Assembly Cache</span></span>](../../app-domains/gac.md)
