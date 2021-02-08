---
description: 'Más información sobre: ICLRDataEnumMemoryRegionsCallback (:: Enummemoryregion ((método)'
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
ms.openlocfilehash: 733911f71898ea7019a0b8d854fb1c1bf61a2474
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801402"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="160d8-103">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion (Método)</span><span class="sxs-lookup"><span data-stu-id="160d8-103">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>

<span data-ttu-id="160d8-104">Llamado por [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) para informar al depurador del resultado de un intento de enumerar un área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="160d8-104">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="160d8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="160d8-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="160d8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="160d8-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="160d8-107">de Dirección inicial de la región de memoria que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="160d8-107">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="160d8-108">de Tamaño, en bytes, de la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="160d8-108">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="160d8-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="160d8-109">Remarks</span></span>  

 <span data-ttu-id="160d8-110">El `ICLRDataEnumMemoryRegions::EnumMemoryRegions` método llamará a este método de devolución de llamada después de cada intento de enumerar una región de memoria.</span><span class="sxs-lookup"><span data-stu-id="160d8-110">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="160d8-111">La enumeración continuará incluso si este método devuelve un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="160d8-111">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="160d8-112">Las regiones que se declaran mediante esta devolución de llamada pueden ser duplicados o regiones superpuestas.</span><span class="sxs-lookup"><span data-stu-id="160d8-112">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="160d8-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="160d8-113">Requirements</span></span>  

 <span data-ttu-id="160d8-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="160d8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="160d8-115">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="160d8-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="160d8-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="160d8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="160d8-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="160d8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="160d8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="160d8-118">See also</span></span>

- [<span data-ttu-id="160d8-119">ICLRDataEnumMemoryRegionsCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="160d8-119">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](iclrdataenummemoryregionscallback-interface.md)
