---
title: ICLRAssemblyReferenceList (Interfaz)
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
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eeef0e7f825f4a6ad907d6b17b92afe1807bad12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="02728-102">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="02728-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="02728-103">Administra una lista de los ensamblados cargados por common language runtime (CLR) y no por el host.</span><span class="sxs-lookup"><span data-stu-id="02728-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02728-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="02728-104">Methods</span></span>  
  
|<span data-ttu-id="02728-105">Método</span><span class="sxs-lookup"><span data-stu-id="02728-105">Method</span></span>|<span data-ttu-id="02728-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="02728-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="02728-107">IsAssemblyReferenceInList (método)</span><span class="sxs-lookup"><span data-stu-id="02728-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="02728-108">Obtiene un valor que indica si el puntero proporcionado hace referencia a un ensamblado en la lista.</span><span class="sxs-lookup"><span data-stu-id="02728-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="02728-109">IsStringAssemblyReferenceInList (método)</span><span class="sxs-lookup"><span data-stu-id="02728-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="02728-110">Obtiene un valor que indica si el nombre proporcionado coincide con el nombre de un ensamblado en la lista.</span><span class="sxs-lookup"><span data-stu-id="02728-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02728-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02728-111">Remarks</span></span>  
 <span data-ttu-id="02728-112">Llame a la [ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) método para obtener un puntero a una instancia de `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="02728-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02728-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02728-113">Requirements</span></span>  
 <span data-ttu-id="02728-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02728-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02728-115">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="02728-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02728-116">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="02728-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02728-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02728-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02728-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="02728-118">See Also</span></span>  
 [<span data-ttu-id="02728-119">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="02728-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="02728-120">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="02728-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="02728-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="02728-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
