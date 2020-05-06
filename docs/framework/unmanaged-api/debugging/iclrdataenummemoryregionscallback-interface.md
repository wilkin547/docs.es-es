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
ms.openlocfilehash: ddcb8064dfb9be30c66404a8762a9ca73cd6afe4
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860664"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="8cf8b-102">ICLRDataEnumMemoryRegionsCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8cf8b-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="8cf8b-103">Proporciona un método de devolución de llamada para [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) con el fin de notificar al depurador el resultado de un intento de enumerar un área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="8cf8b-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8cf8b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8cf8b-104">Methods</span></span>  
  
|<span data-ttu-id="8cf8b-105">Método</span><span class="sxs-lookup"><span data-stu-id="8cf8b-105">Method</span></span>|<span data-ttu-id="8cf8b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8cf8b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8cf8b-107">Método EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="8cf8b-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="8cf8b-108">Llamado por `ICLRDataEnumMemoryRegions::EnumMemoryRegions` para notificar al depurador el resultado de un intento de enumerar un área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="8cf8b-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8cf8b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8cf8b-109">Requirements</span></span>  
 <span data-ttu-id="8cf8b-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cf8b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cf8b-111">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="8cf8b-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8cf8b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cf8b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cf8b-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cf8b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf8b-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8cf8b-114">See also</span></span>

- [<span data-ttu-id="8cf8b-115">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8cf8b-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
