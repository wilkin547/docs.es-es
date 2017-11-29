---
title: CustomDumpItem (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CustomDumpItem
api_location: mscoree.dll
api_type: COM
f1_keywords: CustomDumpItem
helpviewer_keywords: CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 547204385b20d5b7e64bda9ea0a9e790f2ba3471
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="8ece9-102">CustomDumpItem (Estructura)</span><span class="sxs-lookup"><span data-stu-id="8ece9-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="8ece9-103">Describe un elemento que se va a agregar a un volcado personalizado en informes de errores.</span><span class="sxs-lookup"><span data-stu-id="8ece9-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ece9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ece9-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="8ece9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8ece9-105">Members</span></span>  
  
|<span data-ttu-id="8ece9-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="8ece9-106">Member</span></span>|<span data-ttu-id="8ece9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ece9-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="8ece9-108">Un [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) valor que indica el tipo de elemento que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="8ece9-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="8ece9-109">No se están utilizando.</span><span class="sxs-lookup"><span data-stu-id="8ece9-109">Not currently used.</span></span> <span data-ttu-id="8ece9-110">Los elementos agregados a la unión deben ser no mayores que el tamaño del puntero.</span><span class="sxs-lookup"><span data-stu-id="8ece9-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="8ece9-111">Si un `struct` es necesario, debe asignar de forma independiente y apunte a ella.</span><span class="sxs-lookup"><span data-stu-id="8ece9-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ece9-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8ece9-112">Remarks</span></span>  
 <span data-ttu-id="8ece9-113">[ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) toma un parámetro de tipo `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="8ece9-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ece9-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ece9-114">Requirements</span></span>  
 <span data-ttu-id="8ece9-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ece9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ece9-116">**Encabezado:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="8ece9-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="8ece9-117">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8ece9-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ece9-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ece9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ece9-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ece9-119">See Also</span></span>  
 [<span data-ttu-id="8ece9-120">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8ece9-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
