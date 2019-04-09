---
title: CustomDumpItem (Estructura)
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9000f35e9a8f7ecc6c40cf0ef9c220fc9f4f9c10
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185931"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="8833d-102">CustomDumpItem (Estructura)</span><span class="sxs-lookup"><span data-stu-id="8833d-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="8833d-103">Describe un elemento que se agregarán a un volcado personalizado en informes de errores.</span><span class="sxs-lookup"><span data-stu-id="8833d-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8833d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8833d-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="8833d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8833d-105">Members</span></span>  
  
|<span data-ttu-id="8833d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="8833d-106">Member</span></span>|<span data-ttu-id="8833d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8833d-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="8833d-108">Un [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) valor que indica el tipo de elemento que va a agregar.</span><span class="sxs-lookup"><span data-stu-id="8833d-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="8833d-109">No se están utilizando.</span><span class="sxs-lookup"><span data-stu-id="8833d-109">Not currently used.</span></span> <span data-ttu-id="8833d-110">Todos los elementos agregados a la unión no deben ser superior al tamaño del puntero.</span><span class="sxs-lookup"><span data-stu-id="8833d-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="8833d-111">Si un `struct` es necesario, debe asignarlo por separado y apunte a ella.</span><span class="sxs-lookup"><span data-stu-id="8833d-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8833d-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8833d-112">Remarks</span></span>  
 <span data-ttu-id="8833d-113">[ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) toma un parámetro de tipo `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="8833d-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8833d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8833d-114">Requirements</span></span>  
 <span data-ttu-id="8833d-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8833d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8833d-116">**Encabezado**: MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="8833d-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="8833d-117">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8833d-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8833d-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8833d-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8833d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8833d-119">See also</span></span>

- [<span data-ttu-id="8833d-120">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8833d-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
