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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698192"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="484af-102">ICLRDataEnumMemoryRegionsCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="484af-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="484af-103">Proporciona un método de devolución de llamada para [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) para notificar al depurador el resultado de un intento de enumerar un área especificada de memoria.</span><span class="sxs-lookup"><span data-stu-id="484af-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="484af-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="484af-104">Methods</span></span>  
  
|<span data-ttu-id="484af-105">Método</span><span class="sxs-lookup"><span data-stu-id="484af-105">Method</span></span>|<span data-ttu-id="484af-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="484af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="484af-107">EnumMemoryRegion (método)</span><span class="sxs-lookup"><span data-stu-id="484af-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="484af-108">Lo llama `ICLRDataEnumMemoryRegions::EnumMemoryRegions` para notificar al depurador el resultado de un intento de enumerar un área especificada de memoria.</span><span class="sxs-lookup"><span data-stu-id="484af-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="484af-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="484af-109">Requirements</span></span>  
 <span data-ttu-id="484af-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="484af-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="484af-111">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="484af-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="484af-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="484af-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="484af-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="484af-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="484af-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="484af-114">See also</span></span>

- [<span data-ttu-id="484af-115">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="484af-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
