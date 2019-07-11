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
ms.openlocfilehash: 76fc5f578e6da731ffd6406344d00cda8b57f493
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772395"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="1c003-102">EMemoryAvailable (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1c003-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="1c003-103">Contiene valores que indican la cantidad de memoria física disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="1c003-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="1c003-104">Estos valores se asignan lógicamente a los eventos de alta y baja memoria se devuelve desde el `CreateMemoryResourceNotification` función de la API de Windows.</span><span class="sxs-lookup"><span data-stu-id="1c003-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c003-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c003-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="1c003-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="1c003-106">Members</span></span>  
  
|<span data-ttu-id="1c003-107">Member</span><span class="sxs-lookup"><span data-stu-id="1c003-107">Member</span></span>|<span data-ttu-id="1c003-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1c003-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="1c003-109">Una gran cantidad de memoria física está disponible.</span><span class="sxs-lookup"><span data-stu-id="1c003-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="1c003-110">Muy poca memoria física está disponible.</span><span class="sxs-lookup"><span data-stu-id="1c003-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="1c003-111">La memoria física disponible es neutra.</span><span class="sxs-lookup"><span data-stu-id="1c003-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c003-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c003-112">Remarks</span></span>  
 <span data-ttu-id="1c003-113">Este valor se pasa por el host de common language runtime (CLR), mediante una llamada a la [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="1c003-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c003-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c003-114">Requirements</span></span>  
 <span data-ttu-id="1c003-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c003-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c003-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1c003-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c003-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1c003-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c003-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c003-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c003-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c003-119">See also</span></span>

- [<span data-ttu-id="1c003-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="1c003-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
