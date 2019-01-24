---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0ffb85dc5f321e45432d6c2fa9448919957f0e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665206"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="3fd3a-102">EMemoryAvailable (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3fd3a-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="3fd3a-103">Contiene valores que indican la cantidad de memoria física disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3fd3a-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="3fd3a-104">Estos valores se asignan lógicamente a los eventos de alta y baja memoria se devuelve desde el `CreateMemoryResourceNotification` función de la API de Win32.</span><span class="sxs-lookup"><span data-stu-id="3fd3a-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Win32 API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fd3a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3fd3a-105">Syntax</span></span>  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="3fd3a-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="3fd3a-106">Members</span></span>  
  
|<span data-ttu-id="3fd3a-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="3fd3a-107">Member</span></span>|<span data-ttu-id="3fd3a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3fd3a-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="3fd3a-109">Una gran cantidad de memoria física está disponible.</span><span class="sxs-lookup"><span data-stu-id="3fd3a-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="3fd3a-110">Muy poca memoria física está disponible.</span><span class="sxs-lookup"><span data-stu-id="3fd3a-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="3fd3a-111">La memoria física disponible es neutra.</span><span class="sxs-lookup"><span data-stu-id="3fd3a-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fd3a-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3fd3a-112">Remarks</span></span>  
 <span data-ttu-id="3fd3a-113">Este valor se pasa por el host de common language runtime (CLR), mediante una llamada a la [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="3fd3a-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fd3a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3fd3a-114">Requirements</span></span>  
 <span data-ttu-id="3fd3a-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fd3a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fd3a-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3fd3a-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fd3a-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3fd3a-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fd3a-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fd3a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd3a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fd3a-119">See also</span></span>
- [<span data-ttu-id="3fd3a-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="3fd3a-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
