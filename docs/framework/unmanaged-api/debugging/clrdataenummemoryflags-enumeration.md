---
title: "CLRDataEnumMemoryFlags (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRDataEnumMemoryFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CLRDataEnumMemoryFlags
helpviewer_keywords: CLRDataEnumMemoryFlags enumeration [.NET Framework debugging]
ms.assetid: e249f9fc-e24a-4506-903c-92781f6eab7c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c88fe4e6bcbe4f2ec3f13c08450f7dea44ccdbf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="93235-102">CLRDataEnumMemoryFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="93235-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="93235-103">Indica qué regiones de memoria en una llamada a la [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) debe incluir el método.</span><span class="sxs-lookup"><span data-stu-id="93235-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93235-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93235-104">Syntax</span></span>  
  
```  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="93235-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="93235-105">Members</span></span>  
  
|<span data-ttu-id="93235-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="93235-106">Member</span></span>|<span data-ttu-id="93235-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="93235-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="93235-108">Un minivolcado, es decir, un volcado de memoria dispersa.</span><span class="sxs-lookup"><span data-stu-id="93235-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="93235-109">Un volcado de memoria completo.</span><span class="sxs-lookup"><span data-stu-id="93235-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93235-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93235-110">Requirements</span></span>  
 <span data-ttu-id="93235-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93235-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93235-112">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="93235-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="93235-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93235-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93235-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93235-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93235-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="93235-115">See Also</span></span>  
 [<span data-ttu-id="93235-116">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="93235-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
