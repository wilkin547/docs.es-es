---
title: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85b1c5455cb2008a352461d6b506e43fcef48d17
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130928"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="1b73f-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion (Método)</span><span class="sxs-lookup"><span data-stu-id="1b73f-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="1b73f-103">Lo llama [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) para notificar al depurador el resultado de un intento de enumerar un área especificada de memoria.</span><span class="sxs-lookup"><span data-stu-id="1b73f-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b73f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b73f-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b73f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b73f-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="1b73f-106">[in] La dirección inicial de la región de memoria que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="1b73f-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="1b73f-107">[in] El tamaño, en bytes, de la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="1b73f-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b73f-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1b73f-108">Remarks</span></span>  
 <span data-ttu-id="1b73f-109">El `ICLRDataEnumMemoryRegions::EnumMemoryRegions` método llamará a este método de devolución de llamada después de cada intento de enumerar un área de memoria.</span><span class="sxs-lookup"><span data-stu-id="1b73f-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="1b73f-110">La enumeración continuará incluso si este método devuelve un HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="1b73f-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="1b73f-111">Las áreas notificadas por esta devolución de llamada pueden ser duplicados o superpuestas regiones.</span><span class="sxs-lookup"><span data-stu-id="1b73f-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b73f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b73f-112">Requirements</span></span>  
 <span data-ttu-id="1b73f-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b73f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b73f-114">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="1b73f-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1b73f-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b73f-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1b73f-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1b73f-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1b73f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b73f-117">See also</span></span>

- [<span data-ttu-id="1b73f-118">ICLRDataEnumMemoryRegionsCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b73f-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
