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
ms.openlocfilehash: 2ebe7ef37fb072e3688cc4dcfa5ed89832e886e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122934"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="a685f-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion (Método)</span><span class="sxs-lookup"><span data-stu-id="a685f-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="a685f-103">Llamado por [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) para informar al depurador del resultado de un intento de enumerar un área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="a685f-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a685f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a685f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a685f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a685f-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="a685f-106">de Dirección inicial de la región de memoria que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="a685f-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="a685f-107">de Tamaño, en bytes, de la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="a685f-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a685f-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a685f-108">Remarks</span></span>  
 <span data-ttu-id="a685f-109">El método `ICLRDataEnumMemoryRegions::EnumMemoryRegions` llamará a este método de devolución de llamada después de cada intento de enumerar una región de memoria.</span><span class="sxs-lookup"><span data-stu-id="a685f-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="a685f-110">La enumeración continuará incluso si este método devuelve un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="a685f-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="a685f-111">Las regiones que se declaran mediante esta devolución de llamada pueden ser duplicados o regiones superpuestas.</span><span class="sxs-lookup"><span data-stu-id="a685f-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a685f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a685f-112">Requirements</span></span>  
 <span data-ttu-id="a685f-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a685f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a685f-114">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="a685f-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a685f-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a685f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a685f-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a685f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a685f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a685f-117">See also</span></span>

- [<span data-ttu-id="a685f-118">ICLRDataEnumMemoryRegionsCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a685f-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
