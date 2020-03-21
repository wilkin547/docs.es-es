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
ms.openlocfilehash: 154beef9398029f31dcb4d081019b9f292238af4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176479"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="5517b-102">CustomDumpItem (Estructura)</span><span class="sxs-lookup"><span data-stu-id="5517b-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="5517b-103">Describe un elemento que se agregará a un volcado personalizado en los informes de errores.</span><span class="sxs-lookup"><span data-stu-id="5517b-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5517b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5517b-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="5517b-105">Members</span><span class="sxs-lookup"><span data-stu-id="5517b-105">Members</span></span>  
  
|<span data-ttu-id="5517b-106">Member</span><span class="sxs-lookup"><span data-stu-id="5517b-106">Member</span></span>|<span data-ttu-id="5517b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5517b-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="5517b-108">Un [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) valor que indica el tipo de elemento que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="5517b-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="5517b-109">No se usa actualmente.</span><span class="sxs-lookup"><span data-stu-id="5517b-109">Not currently used.</span></span> <span data-ttu-id="5517b-110">Los elementos agregados a la unión no deben ser mayores que el tamaño del puntero.</span><span class="sxs-lookup"><span data-stu-id="5517b-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="5517b-111">Si `struct` se requiere a, debe asignarlo por separado y apuntar a él.</span><span class="sxs-lookup"><span data-stu-id="5517b-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5517b-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5517b-112">Remarks</span></span>  
 <span data-ttu-id="5517b-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) toma un `CustomDumpItem`parámetro de tipo .</span><span class="sxs-lookup"><span data-stu-id="5517b-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5517b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5517b-114">Requirements</span></span>  
 <span data-ttu-id="5517b-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5517b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5517b-116">**Encabezado:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="5517b-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="5517b-117">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5517b-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5517b-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5517b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5517b-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5517b-119">See also</span></span>

- [<span data-ttu-id="5517b-120">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="5517b-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
