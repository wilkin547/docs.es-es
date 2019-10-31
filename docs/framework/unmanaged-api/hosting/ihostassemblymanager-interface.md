---
title: IHostAssemblyManager (Interfaz)
ms.date: 03/30/2017
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
ms.openlocfilehash: d9feeaf5f85d6f84a13e74a893b82c97fdaf023c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124509"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="9702d-102">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9702d-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="9702d-103">Proporciona métodos que permiten a un host especificar conjuntos de ensamblados que deben ser cargados por el Common Language Runtime (CLR) o por el host.</span><span class="sxs-lookup"><span data-stu-id="9702d-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9702d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9702d-104">Methods</span></span>  
  
|<span data-ttu-id="9702d-105">Método</span><span class="sxs-lookup"><span data-stu-id="9702d-105">Method</span></span>|<span data-ttu-id="9702d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9702d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9702d-107">GetAssemblyStore (método)</span><span class="sxs-lookup"><span data-stu-id="9702d-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="9702d-108">Obtiene un puntero de interfaz a un [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) que representa la lista de ensamblados cargados por el host.</span><span class="sxs-lookup"><span data-stu-id="9702d-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="9702d-109">GetNonHostStoreAssemblies (método)</span><span class="sxs-lookup"><span data-stu-id="9702d-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="9702d-110">Obtiene un puntero de interfaz a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) que representa la lista de ensamblados que el host espera que el CLR cargue.</span><span class="sxs-lookup"><span data-stu-id="9702d-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9702d-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9702d-111">Remarks</span></span>  
 <span data-ttu-id="9702d-112">No es necesario que el host implemente `IHostAssemblyManager` o `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="9702d-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="9702d-113">Si el host implementa `IHostAssemblyManager`, también debe implementar `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="9702d-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="9702d-114">El tiempo de ejecución consulta una `IHostAssemblyManager` llamando a [IHostControl:: GetHostManager (](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) al inicializar con una `IID` de IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="9702d-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9702d-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9702d-115">Requirements</span></span>  
 <span data-ttu-id="9702d-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9702d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9702d-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9702d-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9702d-118">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9702d-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9702d-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9702d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9702d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9702d-120">See also</span></span>

- [<span data-ttu-id="9702d-121">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9702d-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="9702d-122">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9702d-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="9702d-123">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9702d-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="9702d-124">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="9702d-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
