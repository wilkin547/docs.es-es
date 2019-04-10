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
ms.openlocfilehash: 80ea3afef4aee51760e3a2ce6a2b895bca4a6ec5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224074"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="ebbb5-102">CLRDataEnumMemoryFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ebbb5-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="ebbb5-103">Indica qué regiones de memoria de una llamada a la [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) debe incluir el método.</span><span class="sxs-lookup"><span data-stu-id="ebbb5-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebbb5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebbb5-104">Syntax</span></span>  
  
```  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ebbb5-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ebbb5-105">Members</span></span>  
  
|<span data-ttu-id="ebbb5-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ebbb5-106">Member</span></span>|<span data-ttu-id="ebbb5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebbb5-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="ebbb5-108">Un minivolcado, es decir, un volcado de memoria dispersa.</span><span class="sxs-lookup"><span data-stu-id="ebbb5-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="ebbb5-109">Un volcado de memoria completo.</span><span class="sxs-lookup"><span data-stu-id="ebbb5-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ebbb5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ebbb5-110">Requirements</span></span>  
 <span data-ttu-id="ebbb5-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebbb5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebbb5-112">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="ebbb5-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ebbb5-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebbb5-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ebbb5-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ebbb5-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ebbb5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebbb5-115">See also</span></span>

- [<span data-ttu-id="ebbb5-116">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="ebbb5-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
