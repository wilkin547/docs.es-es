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
ms.openlocfilehash: 4e3891996af5945ed95c8c37dddfee5c446db248
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789109"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="011de-102">ICLRDataEnumMemoryRegionsCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="011de-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="011de-103">Proporciona un método de devolución de llamada para [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) con el fin de notificar al depurador el resultado de un intento de enumerar un área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="011de-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="011de-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="011de-104">Methods</span></span>  
  
|<span data-ttu-id="011de-105">Método</span><span class="sxs-lookup"><span data-stu-id="011de-105">Method</span></span>|<span data-ttu-id="011de-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="011de-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="011de-107">EnumMemoryRegion (método)</span><span class="sxs-lookup"><span data-stu-id="011de-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="011de-108">Lo llama `ICLRDataEnumMemoryRegions::EnumMemoryRegions` para notificar al depurador el resultado de un intento de enumerar un área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="011de-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="011de-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="011de-109">Requirements</span></span>  
 <span data-ttu-id="011de-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="011de-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="011de-111">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="011de-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="011de-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="011de-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="011de-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="011de-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="011de-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="011de-114">See also</span></span>

- [<span data-ttu-id="011de-115">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="011de-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
