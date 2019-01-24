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
ms.openlocfilehash: 930d56fcfe7cf0d2a128c2068e724b85a224b3fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568925"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="f2076-102">CustomDumpItem (Estructura)</span><span class="sxs-lookup"><span data-stu-id="f2076-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="f2076-103">Describe un elemento que se agregarán a un volcado personalizado en informes de errores.</span><span class="sxs-lookup"><span data-stu-id="f2076-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2076-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2076-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="f2076-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f2076-105">Members</span></span>  
  
|<span data-ttu-id="f2076-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f2076-106">Member</span></span>|<span data-ttu-id="f2076-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2076-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="f2076-108">Un [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) valor que indica el tipo de elemento que va a agregar.</span><span class="sxs-lookup"><span data-stu-id="f2076-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="f2076-109">No se están utilizando.</span><span class="sxs-lookup"><span data-stu-id="f2076-109">Not currently used.</span></span> <span data-ttu-id="f2076-110">Todos los elementos agregados a la unión no deben ser superior al tamaño del puntero.</span><span class="sxs-lookup"><span data-stu-id="f2076-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="f2076-111">Si un `struct` es necesario, debe asignarlo por separado y apunte a ella.</span><span class="sxs-lookup"><span data-stu-id="f2076-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2076-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f2076-112">Remarks</span></span>  
 <span data-ttu-id="f2076-113">[ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) toma un parámetro de tipo `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="f2076-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2076-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2076-114">Requirements</span></span>  
 <span data-ttu-id="f2076-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2076-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2076-116">**Encabezado**: MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="f2076-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f2076-117">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2076-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2076-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2076-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2076-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2076-119">See also</span></span>
- [<span data-ttu-id="f2076-120">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="f2076-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
