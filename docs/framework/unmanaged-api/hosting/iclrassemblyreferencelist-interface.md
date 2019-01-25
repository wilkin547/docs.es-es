---
title: ICLRAssemblyReferenceList (Interfaz)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c2b383abdc67546749867de154a00fda244b3ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660026"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="ffa10-102">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ffa10-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="ffa10-103">Administra una lista de los ensamblados cargados por common language runtime (CLR) y no por el host.</span><span class="sxs-lookup"><span data-stu-id="ffa10-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ffa10-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ffa10-104">Methods</span></span>  
  
|<span data-ttu-id="ffa10-105">Método</span><span class="sxs-lookup"><span data-stu-id="ffa10-105">Method</span></span>|<span data-ttu-id="ffa10-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ffa10-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ffa10-107">IsAssemblyReferenceInList (método)</span><span class="sxs-lookup"><span data-stu-id="ffa10-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="ffa10-108">Obtiene un valor que indica si el puntero proporcionado hace referencia a un ensamblado en la lista.</span><span class="sxs-lookup"><span data-stu-id="ffa10-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="ffa10-109">IsStringAssemblyReferenceInList (método)</span><span class="sxs-lookup"><span data-stu-id="ffa10-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="ffa10-110">Obtiene un valor que indica si el nombre proporcionado coincide con el nombre de un ensamblado en la lista.</span><span class="sxs-lookup"><span data-stu-id="ffa10-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffa10-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ffa10-111">Remarks</span></span>  
 <span data-ttu-id="ffa10-112">Llame a la [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) método para obtener un puntero a una instancia de `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="ffa10-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffa10-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ffa10-113">Requirements</span></span>  
 <span data-ttu-id="ffa10-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffa10-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffa10-115">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ffa10-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffa10-116">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ffa10-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffa10-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffa10-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa10-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ffa10-118">See also</span></span>
- [<span data-ttu-id="ffa10-119">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ffa10-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="ffa10-120">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ffa10-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="ffa10-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ffa10-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
