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
ms.openlocfilehash: 67b85917be590bdba7ed3f10972ad39b731dbcdd
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274246"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="71318-102">CLRDataEnumMemoryFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="71318-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="71318-103">Indica qué regiones de memoria debe incluir una llamada al método [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="71318-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71318-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71318-104">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="71318-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="71318-105">Members</span></span>  
  
|<span data-ttu-id="71318-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="71318-106">Member</span></span>|<span data-ttu-id="71318-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="71318-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="71318-108">Un minivolcado, es decir, un volcado de memoria disperso.</span><span class="sxs-lookup"><span data-stu-id="71318-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="71318-109">Un volcado de memoria completo.</span><span class="sxs-lookup"><span data-stu-id="71318-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71318-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71318-110">Requirements</span></span>  
 <span data-ttu-id="71318-111">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71318-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71318-112">**Encabezado**: ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="71318-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="71318-113">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71318-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71318-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71318-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71318-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="71318-115">See also</span></span>

- [<span data-ttu-id="71318-116">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="71318-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
