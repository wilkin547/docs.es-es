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
ms.openlocfilehash: 4e32a36a4cf751bf7c5a2c918fde0122f21b7878
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501601"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="1f9c0-102">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f9c0-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="1f9c0-103">Proporciona métodos que permiten a un host especificar conjuntos de ensamblados que deben ser cargados por el Common Language Runtime (CLR) o por el host.</span><span class="sxs-lookup"><span data-stu-id="1f9c0-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f9c0-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1f9c0-104">Methods</span></span>  
  
|<span data-ttu-id="1f9c0-105">Método</span><span class="sxs-lookup"><span data-stu-id="1f9c0-105">Method</span></span>|<span data-ttu-id="1f9c0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f9c0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f9c0-107">Método GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="1f9c0-107">GetAssemblyStore Method</span></span>](ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="1f9c0-108">Obtiene un puntero de interfaz a un [IHostAssemblyStore](ihostassemblystore-interface.md) que representa la lista de ensamblados cargados por el host.</span><span class="sxs-lookup"><span data-stu-id="1f9c0-108">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="1f9c0-109">Método GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="1f9c0-109">GetNonHostStoreAssemblies Method</span></span>](ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="1f9c0-110">Obtiene un puntero de interfaz a un [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que representa la lista de ensamblados que el host espera que el CLR cargue.</span><span class="sxs-lookup"><span data-stu-id="1f9c0-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f9c0-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1f9c0-111">Remarks</span></span>  
 <span data-ttu-id="1f9c0-112">No es necesario que el host implemente `IHostAssemblyManager` o `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="1f9c0-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="1f9c0-113">Si el host implementa `IHostAssemblyManager` , también debe implementar `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="1f9c0-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="1f9c0-114">El tiempo de ejecución consulta para un llamando `IHostAssemblyManager` a [IHostControl:: GetHostManager (](ihostcontrol-gethostmanager-method.md) al inicializar con una `IID` de IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="1f9c0-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f9c0-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f9c0-115">Requirements</span></span>  
 <span data-ttu-id="1f9c0-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f9c0-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f9c0-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1f9c0-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1f9c0-118">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1f9c0-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1f9c0-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f9c0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f9c0-120">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="1f9c0-120">See also</span></span>

- [<span data-ttu-id="1f9c0-121">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f9c0-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="1f9c0-122">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f9c0-122">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="1f9c0-123">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f9c0-123">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="1f9c0-124">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="1f9c0-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
