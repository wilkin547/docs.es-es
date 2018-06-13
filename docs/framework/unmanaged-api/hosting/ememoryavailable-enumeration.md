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
ms.openlocfilehash: 139cf540617e278eeaae8a2a5acf10dd797d5d10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429891"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="83b87-102">EMemoryAvailable (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="83b87-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="83b87-103">Contiene valores que indican la cantidad de memoria física libre en el equipo.</span><span class="sxs-lookup"><span data-stu-id="83b87-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="83b87-104">Estos valores lógicamente se asignan a los eventos de alta y baja memoria se devuelve desde el `CreateMemoryResourceNotification` función de la API de Win32.</span><span class="sxs-lookup"><span data-stu-id="83b87-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Win32 API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83b87-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83b87-105">Syntax</span></span>  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="83b87-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="83b87-106">Members</span></span>  
  
|<span data-ttu-id="83b87-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="83b87-107">Member</span></span>|<span data-ttu-id="83b87-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="83b87-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="83b87-109">Una gran cantidad de memoria física está disponible.</span><span class="sxs-lookup"><span data-stu-id="83b87-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="83b87-110">Hay muy poca memoria física.</span><span class="sxs-lookup"><span data-stu-id="83b87-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="83b87-111">La memoria física disponible es neutra.</span><span class="sxs-lookup"><span data-stu-id="83b87-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83b87-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83b87-112">Remarks</span></span>  
 <span data-ttu-id="83b87-113">Este valor se pasa por el host a common language runtime (CLR), mediante una llamada a la [ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="83b87-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83b87-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83b87-114">Requirements</span></span>  
 <span data-ttu-id="83b87-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83b87-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83b87-116">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="83b87-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83b87-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="83b87-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83b87-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83b87-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b87-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="83b87-119">See Also</span></span>  
 [<span data-ttu-id="83b87-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="83b87-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
