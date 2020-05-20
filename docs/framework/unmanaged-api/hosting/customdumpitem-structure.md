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
ms.openlocfilehash: 5c77a332593ba470d2e29b87cba182a770d5db7e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616442"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="ef5f3-102">CustomDumpItem (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ef5f3-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="ef5f3-103">Describe un elemento que se va a agregar a un volcado de memoria personalizado en el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="ef5f3-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef5f3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef5f3-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="ef5f3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ef5f3-105">Members</span></span>  
  
|<span data-ttu-id="ef5f3-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ef5f3-106">Member</span></span>|<span data-ttu-id="ef5f3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef5f3-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="ef5f3-108">Valor de [ecustomdumpitemkind (](ecustomdumpitemkind-enumeration.md) que indica el tipo de elemento que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="ef5f3-108">An [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="ef5f3-109">No se usa actualmente.</span><span class="sxs-lookup"><span data-stu-id="ef5f3-109">Not currently used.</span></span> <span data-ttu-id="ef5f3-110">Los elementos agregados a la Unión no deben ser mayores que el tamaño del puntero.</span><span class="sxs-lookup"><span data-stu-id="ef5f3-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="ef5f3-111">Si `struct` es necesario, debe asignarlo por separado y apuntar a él.</span><span class="sxs-lookup"><span data-stu-id="ef5f3-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef5f3-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ef5f3-112">Remarks</span></span>  
 <span data-ttu-id="ef5f3-113">[ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) toma un parámetro de tipo `CustomDumpItem` .</span><span class="sxs-lookup"><span data-stu-id="ef5f3-113">[ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef5f3-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef5f3-114">Requirements</span></span>  
 <span data-ttu-id="ef5f3-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef5f3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef5f3-116">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="ef5f3-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="ef5f3-117">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ef5f3-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef5f3-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef5f3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef5f3-119">Consulta también</span><span class="sxs-lookup"><span data-stu-id="ef5f3-119">See also</span></span>

- [<span data-ttu-id="ef5f3-120">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ef5f3-120">Hosting Structures</span></span>](hosting-structures.md)
