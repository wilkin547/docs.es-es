---
description: 'Más información acerca de: interfaz ICLRDataEnumMemoryRegionsCallback ('
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
ms.openlocfilehash: 863192844c4d4d8a35d1e73d38adea3a513bc944
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801376"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="062ab-103">ICLRDataEnumMemoryRegionsCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="062ab-103">ICLRDataEnumMemoryRegionsCallback Interface</span></span>

<span data-ttu-id="062ab-104">Proporciona un método de devolución de llamada para [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) con el fin de notificar al depurador el resultado de un intento de enumerar un área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="062ab-104">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="062ab-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="062ab-105">Methods</span></span>  
  
|<span data-ttu-id="062ab-106">Método</span><span class="sxs-lookup"><span data-stu-id="062ab-106">Method</span></span>|<span data-ttu-id="062ab-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="062ab-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="062ab-108">Método EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="062ab-108">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="062ab-109">Llamado por `ICLRDataEnumMemoryRegions::EnumMemoryRegions` para notificar al depurador el resultado de un intento de enumerar un área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="062ab-109">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="062ab-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="062ab-110">Requirements</span></span>  

 <span data-ttu-id="062ab-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="062ab-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="062ab-112">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="062ab-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="062ab-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="062ab-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="062ab-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="062ab-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="062ab-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="062ab-115">See also</span></span>

- [<span data-ttu-id="062ab-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="062ab-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
