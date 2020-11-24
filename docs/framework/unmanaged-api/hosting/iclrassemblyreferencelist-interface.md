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
ms.openlocfilehash: a75235cd0ac0e55412f0ba58881796e3ebc801f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679246"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="ccd0a-102">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccd0a-102">ICLRAssemblyReferenceList Interface</span></span>

<span data-ttu-id="ccd0a-103">Administra una lista de ensamblados cargados por el Common Language Runtime (CLR) y no por el host.</span><span class="sxs-lookup"><span data-stu-id="ccd0a-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ccd0a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ccd0a-104">Methods</span></span>  
  
|<span data-ttu-id="ccd0a-105">Método</span><span class="sxs-lookup"><span data-stu-id="ccd0a-105">Method</span></span>|<span data-ttu-id="ccd0a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ccd0a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ccd0a-107">Método IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="ccd0a-107">IsAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="ccd0a-108">Obtiene un valor que indica si el puntero proporcionado hace referencia a un ensamblado de la lista.</span><span class="sxs-lookup"><span data-stu-id="ccd0a-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="ccd0a-109">Método IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="ccd0a-109">IsStringAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="ccd0a-110">Obtiene un valor que indica si el nombre proporcionado coincide con el nombre de un ensamblado de la lista.</span><span class="sxs-lookup"><span data-stu-id="ccd0a-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccd0a-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ccd0a-111">Remarks</span></span>  

 <span data-ttu-id="ccd0a-112">Llame al método [ICLRAssemblyIdentityManager:: getclrassemblyreferencelist (](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) para obtener un puntero a una instancia de `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="ccd0a-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccd0a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccd0a-113">Requirements</span></span>  

 <span data-ttu-id="ccd0a-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccd0a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccd0a-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ccd0a-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ccd0a-116">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ccd0a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccd0a-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccd0a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd0a-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ccd0a-118">See also</span></span>

- [<span data-ttu-id="ccd0a-119">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccd0a-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="ccd0a-120">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccd0a-120">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="ccd0a-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ccd0a-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
