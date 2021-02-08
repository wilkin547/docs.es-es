---
description: 'Más información sobre: enumeración Ememoryavailable ('
title: EMemoryAvailable (Enumeración)
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: fdb33b45c354d39b1a52fd815a44041b659181ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785454"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="53763-103">EMemoryAvailable (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="53763-103">EMemoryAvailable Enumeration</span></span>

<span data-ttu-id="53763-104">Contiene valores que indican la cantidad de memoria física disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="53763-104">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="53763-105">Estos valores se asignan lógicamente a los eventos de memoria alta y baja devueltas por la `CreateMemoryResourceNotification` función en la API de Windows.</span><span class="sxs-lookup"><span data-stu-id="53763-105">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53763-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53763-106">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="53763-107">Members</span><span class="sxs-lookup"><span data-stu-id="53763-107">Members</span></span>  
  
|<span data-ttu-id="53763-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="53763-108">Member</span></span>|<span data-ttu-id="53763-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="53763-109">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="53763-110">Hay mucha memoria física disponible.</span><span class="sxs-lookup"><span data-stu-id="53763-110">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="53763-111">Hay muy poca memoria física disponible.</span><span class="sxs-lookup"><span data-stu-id="53763-111">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="53763-112">La memoria física disponible es neutra.</span><span class="sxs-lookup"><span data-stu-id="53763-112">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53763-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="53763-113">Remarks</span></span>  

 <span data-ttu-id="53763-114">El host pasa este valor al Common Language Runtime (CLR) mediante una llamada al método [ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="53763-114">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53763-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53763-115">Requirements</span></span>  

 <span data-ttu-id="53763-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53763-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53763-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="53763-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53763-118">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="53763-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53763-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53763-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53763-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="53763-120">See also</span></span>

- [<span data-ttu-id="53763-121">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="53763-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
