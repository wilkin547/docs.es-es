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
ms.openlocfilehash: c8313b7c97eb5d94424259dc91459f62e13368fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785595"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="39bf5-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion (Método)</span><span class="sxs-lookup"><span data-stu-id="39bf5-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="39bf5-103">Llamado por [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) para informar al depurador del resultado de un intento de enumerar un área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="39bf5-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39bf5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39bf5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39bf5-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="39bf5-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="39bf5-106">de Dirección inicial de la región de memoria que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="39bf5-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="39bf5-107">de Tamaño, en bytes, de la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="39bf5-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39bf5-108">Notas</span><span class="sxs-lookup"><span data-stu-id="39bf5-108">Remarks</span></span>  
 <span data-ttu-id="39bf5-109">El método `ICLRDataEnumMemoryRegions::EnumMemoryRegions` llamará a este método de devolución de llamada después de cada intento de enumerar una región de memoria.</span><span class="sxs-lookup"><span data-stu-id="39bf5-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="39bf5-110">La enumeración continuará incluso si este método devuelve un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="39bf5-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="39bf5-111">Las regiones que se declaran mediante esta devolución de llamada pueden ser duplicados o regiones superpuestas.</span><span class="sxs-lookup"><span data-stu-id="39bf5-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39bf5-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="39bf5-112">Requirements</span></span>  
 <span data-ttu-id="39bf5-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39bf5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39bf5-114">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="39bf5-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="39bf5-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39bf5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39bf5-116">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39bf5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39bf5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="39bf5-117">See also</span></span>

- [<span data-ttu-id="39bf5-118">ICLRDataEnumMemoryRegionsCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="39bf5-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](iclrdataenummemoryregionscallback-interface.md)
