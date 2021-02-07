---
description: 'Más información acerca de: estructura Customdumpitem ('
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
ms.openlocfilehash: 9bd7b2bb59675bc01e24dc6e6d0ce524f3d35466
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716905"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="7cece-103">CustomDumpItem (Estructura)</span><span class="sxs-lookup"><span data-stu-id="7cece-103">CustomDumpItem Structure</span></span>

<span data-ttu-id="7cece-104">Describe un elemento que se va a agregar a un volcado de memoria personalizado en el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="7cece-104">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cece-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7cece-105">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="7cece-106">Members</span><span class="sxs-lookup"><span data-stu-id="7cece-106">Members</span></span>  
  
|<span data-ttu-id="7cece-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="7cece-107">Member</span></span>|<span data-ttu-id="7cece-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7cece-108">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="7cece-109">Valor de [ecustomdumpitemkind (](ecustomdumpitemkind-enumeration.md) que indica el tipo de elemento que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="7cece-109">An [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="7cece-110">No se usa actualmente.</span><span class="sxs-lookup"><span data-stu-id="7cece-110">Not currently used.</span></span> <span data-ttu-id="7cece-111">Los elementos agregados a la Unión no deben ser mayores que el tamaño del puntero.</span><span class="sxs-lookup"><span data-stu-id="7cece-111">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="7cece-112">Si `struct` es necesario, debe asignarlo por separado y apuntar a él.</span><span class="sxs-lookup"><span data-stu-id="7cece-112">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cece-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7cece-113">Remarks</span></span>  

 <span data-ttu-id="7cece-114">[ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) toma un parámetro de tipo `CustomDumpItem` .</span><span class="sxs-lookup"><span data-stu-id="7cece-114">[ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cece-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7cece-115">Requirements</span></span>  

 <span data-ttu-id="7cece-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cece-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cece-117">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="7cece-117">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="7cece-118">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7cece-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7cece-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cece-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cece-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cece-120">See also</span></span>

- [<span data-ttu-id="7cece-121">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="7cece-121">Hosting Structures</span></span>](hosting-structures.md)
