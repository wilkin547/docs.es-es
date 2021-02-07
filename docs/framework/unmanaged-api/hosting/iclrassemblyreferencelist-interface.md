---
description: 'Más información sobre: interfaz ICLRAssemblyReferenceList'
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
ms.openlocfilehash: f5ef4efd343ebc18c443482f4697a3d299c5aac1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716829"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="540bc-103">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="540bc-103">ICLRAssemblyReferenceList Interface</span></span>

<span data-ttu-id="540bc-104">Administra una lista de ensamblados cargados por el Common Language Runtime (CLR) y no por el host.</span><span class="sxs-lookup"><span data-stu-id="540bc-104">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="540bc-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="540bc-105">Methods</span></span>  
  
|<span data-ttu-id="540bc-106">Método</span><span class="sxs-lookup"><span data-stu-id="540bc-106">Method</span></span>|<span data-ttu-id="540bc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="540bc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="540bc-108">Método IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="540bc-108">IsAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="540bc-109">Obtiene un valor que indica si el puntero proporcionado hace referencia a un ensamblado de la lista.</span><span class="sxs-lookup"><span data-stu-id="540bc-109">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="540bc-110">Método IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="540bc-110">IsStringAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="540bc-111">Obtiene un valor que indica si el nombre proporcionado coincide con el nombre de un ensamblado de la lista.</span><span class="sxs-lookup"><span data-stu-id="540bc-111">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="540bc-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="540bc-112">Remarks</span></span>  

 <span data-ttu-id="540bc-113">Llame al método [ICLRAssemblyIdentityManager:: getclrassemblyreferencelist (](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) para obtener un puntero a una instancia de `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="540bc-113">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="540bc-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="540bc-114">Requirements</span></span>  

 <span data-ttu-id="540bc-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="540bc-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="540bc-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="540bc-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="540bc-117">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="540bc-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="540bc-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="540bc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="540bc-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="540bc-119">See also</span></span>

- [<span data-ttu-id="540bc-120">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="540bc-120">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="540bc-121">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="540bc-121">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="540bc-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="540bc-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
