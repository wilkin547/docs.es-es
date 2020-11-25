---
title: ICLRDataEnumMemoryRegionsCallback (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
ms.openlocfilehash: f080d852b190346740a3629f3b5d46a9f3808293
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703635"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="7d23c-102">ICLRDataEnumMemoryRegionsCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d23c-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>

<span data-ttu-id="7d23c-103">Proporciona un método de devolución de llamada para [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) con el fin de notificar al depurador el resultado de un intento de enumerar un área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="7d23c-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7d23c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7d23c-104">Methods</span></span>  
  
|<span data-ttu-id="7d23c-105">Método</span><span class="sxs-lookup"><span data-stu-id="7d23c-105">Method</span></span>|<span data-ttu-id="7d23c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d23c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7d23c-107">Método EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="7d23c-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="7d23c-108">Llamado por `ICLRDataEnumMemoryRegions::EnumMemoryRegions` para notificar al depurador el resultado de un intento de enumerar un área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="7d23c-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d23c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d23c-109">Requirements</span></span>  

 <span data-ttu-id="7d23c-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d23c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d23c-111">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="7d23c-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7d23c-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d23c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d23c-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d23c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d23c-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d23c-114">See also</span></span>

- [<span data-ttu-id="7d23c-115">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="7d23c-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
