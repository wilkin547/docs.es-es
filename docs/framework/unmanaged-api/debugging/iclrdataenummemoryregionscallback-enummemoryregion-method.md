---
title: "ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1b1897b18a8dcbb261a5041ca8b530b7877b910
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="01efb-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion (Método)</span><span class="sxs-lookup"><span data-stu-id="01efb-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="01efb-103">Llamado por el método [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) para notificar al depurador el resultado de un intento de enumerar un área especificada de memoria.</span><span class="sxs-lookup"><span data-stu-id="01efb-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01efb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01efb-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01efb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="01efb-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="01efb-106">[in] La dirección inicial de la región de memoria que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="01efb-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="01efb-107">[in] El tamaño, en bytes, de la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="01efb-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01efb-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="01efb-108">Remarks</span></span>  
 <span data-ttu-id="01efb-109">El `ICLRDataEnumMemoryRegions::EnumMemoryRegions` método llamará a este método de devolución de llamada después de cada intento de enumerar un área de memoria.</span><span class="sxs-lookup"><span data-stu-id="01efb-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="01efb-110">La enumeración continuará incluso si este método devuelve un HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="01efb-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="01efb-111">Las áreas notificadas por esta devolución de llamada pueden ser duplicados o las áreas superpuestas.</span><span class="sxs-lookup"><span data-stu-id="01efb-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01efb-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01efb-112">Requirements</span></span>  
 <span data-ttu-id="01efb-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01efb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01efb-114">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="01efb-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="01efb-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01efb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01efb-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01efb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01efb-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="01efb-117">See Also</span></span>  
 [<span data-ttu-id="01efb-118">ICLRDataEnumMemoryRegionsCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="01efb-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
