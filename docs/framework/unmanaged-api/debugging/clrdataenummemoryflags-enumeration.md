---
description: 'Más información sobre: enumeración Clrdataenummemoryflags ('
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
ms.openlocfilehash: 3522649c59177de8295416ce260c374df605efb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662252"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="9cc0c-103">CLRDataEnumMemoryFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9cc0c-103">CLRDataEnumMemoryFlags Enumeration</span></span>

<span data-ttu-id="9cc0c-104">Indica qué regiones de memoria debe incluir una llamada al método [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9cc0c-104">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cc0c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9cc0c-105">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9cc0c-106">Members</span><span class="sxs-lookup"><span data-stu-id="9cc0c-106">Members</span></span>  
  
|<span data-ttu-id="9cc0c-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="9cc0c-107">Member</span></span>|<span data-ttu-id="9cc0c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9cc0c-108">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="9cc0c-109">Un minivolcado, es decir, un volcado de memoria disperso.</span><span class="sxs-lookup"><span data-stu-id="9cc0c-109">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="9cc0c-110">Un volcado de memoria completo.</span><span class="sxs-lookup"><span data-stu-id="9cc0c-110">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9cc0c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9cc0c-111">Requirements</span></span>  

 <span data-ttu-id="9cc0c-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cc0c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cc0c-113">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="9cc0c-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="9cc0c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cc0c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cc0c-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cc0c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cc0c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9cc0c-116">See also</span></span>

- [<span data-ttu-id="9cc0c-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="9cc0c-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
