---
title: CLRDataEnumMemoryFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CLRDataEnumMemoryFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLRDataEnumMemoryFlags
helpviewer_keywords:
- CLRDataEnumMemoryFlags enumeration [.NET Framework debugging]
ms.assetid: e249f9fc-e24a-4506-903c-92781f6eab7c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cd385c1176bea41b41a981e743c6104227d8acd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708199"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="77c97-102">CLRDataEnumMemoryFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="77c97-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="77c97-103">Indica qué regiones de memoria de una llamada a la [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) debe incluir el método.</span><span class="sxs-lookup"><span data-stu-id="77c97-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77c97-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77c97-104">Syntax</span></span>  
  
```  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="77c97-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="77c97-105">Members</span></span>  
  
|<span data-ttu-id="77c97-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="77c97-106">Member</span></span>|<span data-ttu-id="77c97-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="77c97-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="77c97-108">Un minivolcado, es decir, un volcado de memoria dispersa.</span><span class="sxs-lookup"><span data-stu-id="77c97-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="77c97-109">Un volcado de memoria completo.</span><span class="sxs-lookup"><span data-stu-id="77c97-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77c97-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77c97-110">Requirements</span></span>  
 <span data-ttu-id="77c97-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77c97-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77c97-112">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="77c97-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="77c97-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77c97-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77c97-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77c97-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77c97-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="77c97-115">See also</span></span>
- [<span data-ttu-id="77c97-116">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="77c97-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
