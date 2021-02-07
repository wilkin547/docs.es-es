---
description: 'Más información acerca de: IHostAssemblyManager (interfaz)'
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
ms.openlocfilehash: 649771f79e65039adfa8c0ade9f167b1679bb917
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709001"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="53fa6-103">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="53fa6-103">IHostAssemblyManager Interface</span></span>

<span data-ttu-id="53fa6-104">Proporciona métodos que permiten a un host especificar conjuntos de ensamblados que deben ser cargados por el Common Language Runtime (CLR) o por el host.</span><span class="sxs-lookup"><span data-stu-id="53fa6-104">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53fa6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="53fa6-105">Methods</span></span>  
  
|<span data-ttu-id="53fa6-106">Método</span><span class="sxs-lookup"><span data-stu-id="53fa6-106">Method</span></span>|<span data-ttu-id="53fa6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="53fa6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53fa6-108">Método GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="53fa6-108">GetAssemblyStore Method</span></span>](ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="53fa6-109">Obtiene un puntero de interfaz a un [IHostAssemblyStore](ihostassemblystore-interface.md) que representa la lista de ensamblados cargados por el host.</span><span class="sxs-lookup"><span data-stu-id="53fa6-109">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="53fa6-110">Método GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="53fa6-110">GetNonHostStoreAssemblies Method</span></span>](ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="53fa6-111">Obtiene un puntero de interfaz a un [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que representa la lista de ensamblados que el host espera que el CLR cargue.</span><span class="sxs-lookup"><span data-stu-id="53fa6-111">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53fa6-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="53fa6-112">Remarks</span></span>  

 <span data-ttu-id="53fa6-113">No es necesario que el host implemente `IHostAssemblyManager` o `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="53fa6-113">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="53fa6-114">Si el host implementa `IHostAssemblyManager` , también debe implementar `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="53fa6-114">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="53fa6-115">El tiempo de ejecución consulta para un llamando `IHostAssemblyManager` a [IHostControl:: GetHostManager (](ihostcontrol-gethostmanager-method.md) al inicializar con una `IID` de IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="53fa6-115">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53fa6-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53fa6-116">Requirements</span></span>  

 <span data-ttu-id="53fa6-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53fa6-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53fa6-118">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="53fa6-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53fa6-119">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="53fa6-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53fa6-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53fa6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53fa6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="53fa6-121">See also</span></span>

- [<span data-ttu-id="53fa6-122">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="53fa6-122">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="53fa6-123">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="53fa6-123">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="53fa6-124">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="53fa6-124">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="53fa6-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="53fa6-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
