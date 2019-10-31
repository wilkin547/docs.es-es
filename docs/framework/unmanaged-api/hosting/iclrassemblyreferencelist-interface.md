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
ms.openlocfilehash: e74d49d71cfee51f8cb99645151aace3d02de0e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126665"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="de06a-102">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="de06a-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="de06a-103">Administra una lista de ensamblados cargados por el Common Language Runtime (CLR) y no por el host.</span><span class="sxs-lookup"><span data-stu-id="de06a-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de06a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="de06a-104">Methods</span></span>  
  
|<span data-ttu-id="de06a-105">Método</span><span class="sxs-lookup"><span data-stu-id="de06a-105">Method</span></span>|<span data-ttu-id="de06a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="de06a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de06a-107">IsAssemblyReferenceInList (método)</span><span class="sxs-lookup"><span data-stu-id="de06a-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="de06a-108">Obtiene un valor que indica si el puntero proporcionado hace referencia a un ensamblado de la lista.</span><span class="sxs-lookup"><span data-stu-id="de06a-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="de06a-109">IsStringAssemblyReferenceInList (método)</span><span class="sxs-lookup"><span data-stu-id="de06a-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="de06a-110">Obtiene un valor que indica si el nombre proporcionado coincide con el nombre de un ensamblado de la lista.</span><span class="sxs-lookup"><span data-stu-id="de06a-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de06a-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de06a-111">Remarks</span></span>  
 <span data-ttu-id="de06a-112">Llame al método [ICLRAssemblyIdentityManager:: getclrassemblyreferencelist (](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) para obtener un puntero a una instancia de `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="de06a-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de06a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de06a-113">Requirements</span></span>  
 <span data-ttu-id="de06a-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de06a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de06a-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="de06a-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="de06a-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="de06a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de06a-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de06a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de06a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="de06a-118">See also</span></span>

- [<span data-ttu-id="de06a-119">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="de06a-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="de06a-120">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="de06a-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="de06a-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="de06a-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
