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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dad66c8a55982762ede754a4b3cd747b7a91b87d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225435"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="33416-102">ICLRDataEnumMemoryRegionsCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33416-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="33416-103">Proporciona un método de devolución de llamada para [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) para notificar al depurador el resultado de un intento de enumerar un área especificada de memoria.</span><span class="sxs-lookup"><span data-stu-id="33416-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33416-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="33416-104">Methods</span></span>  
  
|<span data-ttu-id="33416-105">Método</span><span class="sxs-lookup"><span data-stu-id="33416-105">Method</span></span>|<span data-ttu-id="33416-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="33416-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33416-107">Método EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="33416-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="33416-108">Lo llama `ICLRDataEnumMemoryRegions::EnumMemoryRegions` para notificar al depurador el resultado de un intento de enumerar un área especificada de memoria.</span><span class="sxs-lookup"><span data-stu-id="33416-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33416-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33416-109">Requirements</span></span>  
 <span data-ttu-id="33416-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33416-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33416-111">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="33416-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="33416-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33416-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="33416-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="33416-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33416-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="33416-114">See also</span></span>

- [<span data-ttu-id="33416-115">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="33416-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
