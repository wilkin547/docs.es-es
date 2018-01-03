---
title: "ICLRDataEnumMemoryRegions::EnumMemoryRegions (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1685b1f739519485e5e68928b29a874587e6f9c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="e5cea-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions (Método)</span><span class="sxs-lookup"><span data-stu-id="e5cea-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="e5cea-103">Enumera áreas específicas de la memoria.</span><span class="sxs-lookup"><span data-stu-id="e5cea-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5cea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5cea-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5cea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5cea-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="e5cea-106">[in] Un puntero a un [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instancia que llama a este método para cada región de memoria que se va a enumerar para notificar al depurador el resultado.</span><span class="sxs-lookup"><span data-stu-id="e5cea-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="e5cea-107">La enumeración de regiones de memoria continúa incluso si la devolución de llamada indica un error.</span><span class="sxs-lookup"><span data-stu-id="e5cea-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="e5cea-108">[in] No usado.</span><span class="sxs-lookup"><span data-stu-id="e5cea-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="e5cea-109">[in] Un valor de la [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeración que especifica las regiones de memoria que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="e5cea-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5cea-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5cea-110">Remarks</span></span>  
 <span data-ttu-id="e5cea-111">Este método usa especificado [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instancia para notificar al llamador de resultados.</span><span class="sxs-lookup"><span data-stu-id="e5cea-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5cea-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5cea-112">Requirements</span></span>  
 <span data-ttu-id="e5cea-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5cea-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5cea-114">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e5cea-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e5cea-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5cea-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5cea-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5cea-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5cea-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5cea-117">See Also</span></span>  
 [<span data-ttu-id="e5cea-118">ICLRDataEnumMemoryRegions (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5cea-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
