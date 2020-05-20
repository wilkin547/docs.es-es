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
ms.openlocfilehash: f1aa40ef868bf6ff7730e01ab66a6fec58af1196
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615883"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="94605-102">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94605-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="94605-103">Administra una lista de ensamblados cargados por el Common Language Runtime (CLR) y no por el host.</span><span class="sxs-lookup"><span data-stu-id="94605-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94605-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="94605-104">Methods</span></span>  
  
|<span data-ttu-id="94605-105">Método</span><span class="sxs-lookup"><span data-stu-id="94605-105">Method</span></span>|<span data-ttu-id="94605-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="94605-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94605-107">Método IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="94605-107">IsAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="94605-108">Obtiene un valor que indica si el puntero proporcionado hace referencia a un ensamblado de la lista.</span><span class="sxs-lookup"><span data-stu-id="94605-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="94605-109">Método IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="94605-109">IsStringAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="94605-110">Obtiene un valor que indica si el nombre proporcionado coincide con el nombre de un ensamblado de la lista.</span><span class="sxs-lookup"><span data-stu-id="94605-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94605-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="94605-111">Remarks</span></span>  
 <span data-ttu-id="94605-112">Llame al método [ICLRAssemblyIdentityManager:: getclrassemblyreferencelist (](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) para obtener un puntero a una instancia de `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="94605-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94605-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94605-113">Requirements</span></span>  
 <span data-ttu-id="94605-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94605-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94605-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="94605-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94605-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="94605-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94605-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94605-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94605-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="94605-118">See also</span></span>

- [<span data-ttu-id="94605-119">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94605-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="94605-120">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94605-120">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="94605-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="94605-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
