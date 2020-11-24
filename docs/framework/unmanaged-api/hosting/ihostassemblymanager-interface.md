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
ms.openlocfilehash: a06e7f13b6de9450aa2a81f28f591c0a3ce8db0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681007"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="bb6c2-102">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb6c2-102">IHostAssemblyManager Interface</span></span>

<span data-ttu-id="bb6c2-103">Proporciona métodos que permiten a un host especificar conjuntos de ensamblados que deben ser cargados por el Common Language Runtime (CLR) o por el host.</span><span class="sxs-lookup"><span data-stu-id="bb6c2-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb6c2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="bb6c2-104">Methods</span></span>  
  
|<span data-ttu-id="bb6c2-105">Método</span><span class="sxs-lookup"><span data-stu-id="bb6c2-105">Method</span></span>|<span data-ttu-id="bb6c2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb6c2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb6c2-107">Método GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="bb6c2-107">GetAssemblyStore Method</span></span>](ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="bb6c2-108">Obtiene un puntero de interfaz a un [IHostAssemblyStore](ihostassemblystore-interface.md) que representa la lista de ensamblados cargados por el host.</span><span class="sxs-lookup"><span data-stu-id="bb6c2-108">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="bb6c2-109">Método GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="bb6c2-109">GetNonHostStoreAssemblies Method</span></span>](ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="bb6c2-110">Obtiene un puntero de interfaz a un [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que representa la lista de ensamblados que el host espera que el CLR cargue.</span><span class="sxs-lookup"><span data-stu-id="bb6c2-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb6c2-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb6c2-111">Remarks</span></span>  

 <span data-ttu-id="bb6c2-112">No es necesario que el host implemente `IHostAssemblyManager` o `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="bb6c2-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="bb6c2-113">Si el host implementa `IHostAssemblyManager` , también debe implementar `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="bb6c2-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="bb6c2-114">El tiempo de ejecución consulta para un llamando `IHostAssemblyManager` a [IHostControl:: GetHostManager (](ihostcontrol-gethostmanager-method.md) al inicializar con una `IID` de IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="bb6c2-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb6c2-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb6c2-115">Requirements</span></span>  

 <span data-ttu-id="bb6c2-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb6c2-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb6c2-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bb6c2-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bb6c2-118">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb6c2-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb6c2-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb6c2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb6c2-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb6c2-120">See also</span></span>

- [<span data-ttu-id="bb6c2-121">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb6c2-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="bb6c2-122">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb6c2-122">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="bb6c2-123">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb6c2-123">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="bb6c2-124">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="bb6c2-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
