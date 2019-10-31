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
ms.openlocfilehash: aec3c5f140df7eab10ea2bfa33634a4d853adcb0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134288"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="1e60b-102">EMemoryAvailable (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1e60b-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="1e60b-103">Contiene valores que indican la cantidad de memoria física disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="1e60b-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="1e60b-104">Estos valores se asignan lógicamente a los eventos de memoria alta y baja devueltas por la función `CreateMemoryResourceNotification` de la API de Windows.</span><span class="sxs-lookup"><span data-stu-id="1e60b-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e60b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e60b-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="1e60b-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="1e60b-106">Members</span></span>  
  
|<span data-ttu-id="1e60b-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="1e60b-107">Member</span></span>|<span data-ttu-id="1e60b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e60b-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="1e60b-109">Hay mucha memoria física disponible.</span><span class="sxs-lookup"><span data-stu-id="1e60b-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="1e60b-110">Hay muy poca memoria física disponible.</span><span class="sxs-lookup"><span data-stu-id="1e60b-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="1e60b-111">La memoria física disponible es neutra.</span><span class="sxs-lookup"><span data-stu-id="1e60b-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e60b-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1e60b-112">Remarks</span></span>  
 <span data-ttu-id="1e60b-113">El host pasa este valor al Common Language Runtime (CLR) mediante una llamada al método [ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1e60b-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e60b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e60b-114">Requirements</span></span>  
 <span data-ttu-id="1e60b-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e60b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e60b-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1e60b-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e60b-117">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1e60b-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e60b-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e60b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e60b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e60b-119">See also</span></span>

- [<span data-ttu-id="1e60b-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="1e60b-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
