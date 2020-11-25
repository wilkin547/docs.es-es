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
ms.openlocfilehash: b5ca524d223fad7ded0d56def3293eb40be69fa0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703725"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="3bfb3-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion (Método)</span><span class="sxs-lookup"><span data-stu-id="3bfb3-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>

<span data-ttu-id="3bfb3-103">Llamado por [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) para informar al depurador del resultado de un intento de enumerar un área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="3bfb3-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bfb3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bfb3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bfb3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3bfb3-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="3bfb3-106">de Dirección inicial de la región de memoria que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="3bfb3-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="3bfb3-107">de Tamaño, en bytes, de la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="3bfb3-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bfb3-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3bfb3-108">Remarks</span></span>  

 <span data-ttu-id="3bfb3-109">El `ICLRDataEnumMemoryRegions::EnumMemoryRegions` método llamará a este método de devolución de llamada después de cada intento de enumerar una región de memoria.</span><span class="sxs-lookup"><span data-stu-id="3bfb3-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="3bfb3-110">La enumeración continuará incluso si este método devuelve un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="3bfb3-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="3bfb3-111">Las regiones que se declaran mediante esta devolución de llamada pueden ser duplicados o regiones superpuestas.</span><span class="sxs-lookup"><span data-stu-id="3bfb3-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bfb3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bfb3-112">Requirements</span></span>  

 <span data-ttu-id="3bfb3-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bfb3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bfb3-114">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="3bfb3-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3bfb3-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bfb3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3bfb3-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bfb3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bfb3-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3bfb3-117">See also</span></span>

- [<span data-ttu-id="3bfb3-118">ICLRDataEnumMemoryRegionsCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bfb3-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](iclrdataenummemoryregionscallback-interface.md)
