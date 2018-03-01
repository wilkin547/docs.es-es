---
title: IHostAssemblyManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 351824c1b915183a8e157f5bb2e01a414027a178
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="a53bc-102">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a53bc-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="a53bc-103">Proporciona métodos que permiten a un host especificar los conjuntos de ensamblados que se deben cargar por common language runtime (CLR) o el host.</span><span class="sxs-lookup"><span data-stu-id="a53bc-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a53bc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a53bc-104">Methods</span></span>  
  
|<span data-ttu-id="a53bc-105">Método</span><span class="sxs-lookup"><span data-stu-id="a53bc-105">Method</span></span>|<span data-ttu-id="a53bc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a53bc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a53bc-107">GetAssemblyStore (método)</span><span class="sxs-lookup"><span data-stu-id="a53bc-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="a53bc-108">Obtiene un puntero de interfaz a una [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) que representa la lista de ensamblados cargados por el host.</span><span class="sxs-lookup"><span data-stu-id="a53bc-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="a53bc-109">GetNonHostStoreAssemblies (método)</span><span class="sxs-lookup"><span data-stu-id="a53bc-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="a53bc-110">Obtiene un puntero de interfaz a una [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) que representa la lista de ensamblados que el host espera que CLR cargue.</span><span class="sxs-lookup"><span data-stu-id="a53bc-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a53bc-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a53bc-111">Remarks</span></span>  
 <span data-ttu-id="a53bc-112">El host no tiene que implementar `IHostAssemblyManager` o `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="a53bc-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="a53bc-113">Si el host implementa `IHostAssemblyManager`, también debe implementar `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="a53bc-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="a53bc-114">El tiempo de ejecución de consulta para un `IHostAssemblyManager` mediante una llamada a [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) tras la inicialización con una `IID` de IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="a53bc-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a53bc-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a53bc-115">Requirements</span></span>  
 <span data-ttu-id="a53bc-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a53bc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a53bc-117">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a53bc-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a53bc-118">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a53bc-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a53bc-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a53bc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a53bc-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a53bc-120">See Also</span></span>  
 [<span data-ttu-id="a53bc-121">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a53bc-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="a53bc-122">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a53bc-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="a53bc-123">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a53bc-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="a53bc-124">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a53bc-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
