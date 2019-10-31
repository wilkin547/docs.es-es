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
ms.openlocfilehash: ae64edd8a3a628100d4c51d0b78be1bc8d49fc17
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138278"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="76718-102">CustomDumpItem (Estructura)</span><span class="sxs-lookup"><span data-stu-id="76718-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="76718-103">Describe un elemento que se va a agregar a un volcado de memoria personalizado en el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="76718-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76718-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76718-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="76718-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="76718-105">Members</span></span>  
  
|<span data-ttu-id="76718-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="76718-106">Member</span></span>|<span data-ttu-id="76718-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="76718-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="76718-108">Valor de [ecustomdumpitemkind (](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) que indica el tipo de elemento que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="76718-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="76718-109">No se usa actualmente.</span><span class="sxs-lookup"><span data-stu-id="76718-109">Not currently used.</span></span> <span data-ttu-id="76718-110">Los elementos agregados a la Unión no deben ser mayores que el tamaño del puntero.</span><span class="sxs-lookup"><span data-stu-id="76718-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="76718-111">Si se requiere un `struct`, debe asignarlo por separado y apuntar a él.</span><span class="sxs-lookup"><span data-stu-id="76718-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76718-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76718-112">Remarks</span></span>  
 <span data-ttu-id="76718-113">[ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) toma un parámetro de tipo `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="76718-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76718-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76718-114">Requirements</span></span>  
 <span data-ttu-id="76718-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76718-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76718-116">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="76718-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="76718-117">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="76718-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76718-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76718-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76718-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="76718-119">See also</span></span>

- [<span data-ttu-id="76718-120">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="76718-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
