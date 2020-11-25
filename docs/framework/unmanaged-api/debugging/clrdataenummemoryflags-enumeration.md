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
ms.openlocfilehash: 9a82162023fa05e85fc9bbeb16961f2aafd9a4ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729803"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="89cc8-102">CLRDataEnumMemoryFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="89cc8-102">CLRDataEnumMemoryFlags Enumeration</span></span>

<span data-ttu-id="89cc8-103">Indica qué regiones de memoria debe incluir una llamada al método [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="89cc8-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89cc8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89cc8-104">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="89cc8-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="89cc8-105">Members</span></span>  
  
|<span data-ttu-id="89cc8-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="89cc8-106">Member</span></span>|<span data-ttu-id="89cc8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="89cc8-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="89cc8-108">Un minivolcado, es decir, un volcado de memoria disperso.</span><span class="sxs-lookup"><span data-stu-id="89cc8-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="89cc8-109">Un volcado de memoria completo.</span><span class="sxs-lookup"><span data-stu-id="89cc8-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="89cc8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89cc8-110">Requirements</span></span>  

 <span data-ttu-id="89cc8-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89cc8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89cc8-112">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="89cc8-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="89cc8-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89cc8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89cc8-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89cc8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89cc8-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89cc8-115">See also</span></span>

- [<span data-ttu-id="89cc8-116">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="89cc8-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
