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
ms.openlocfilehash: d98a0c1c3187b81c44fae6eee91d975169a40045
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072811"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="04e59-102">EMemoryAvailable (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="04e59-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="04e59-103">Contiene valores que indican la cantidad de memoria física disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="04e59-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="04e59-104">Estos valores se asignan lógicamente a los eventos de alta y baja memoria se devuelve desde el `CreateMemoryResourceNotification` función de la API de Windows.</span><span class="sxs-lookup"><span data-stu-id="04e59-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04e59-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04e59-105">Syntax</span></span>  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="04e59-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="04e59-106">Members</span></span>  
  
|<span data-ttu-id="04e59-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="04e59-107">Member</span></span>|<span data-ttu-id="04e59-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="04e59-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="04e59-109">Una gran cantidad de memoria física está disponible.</span><span class="sxs-lookup"><span data-stu-id="04e59-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="04e59-110">Muy poca memoria física está disponible.</span><span class="sxs-lookup"><span data-stu-id="04e59-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="04e59-111">La memoria física disponible es neutra.</span><span class="sxs-lookup"><span data-stu-id="04e59-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04e59-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04e59-112">Remarks</span></span>  
 <span data-ttu-id="04e59-113">Este valor se pasa por el host de common language runtime (CLR), mediante una llamada a la [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="04e59-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04e59-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04e59-114">Requirements</span></span>  
 <span data-ttu-id="04e59-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04e59-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04e59-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="04e59-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04e59-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04e59-117">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="04e59-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="04e59-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="04e59-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="04e59-119">See also</span></span>

- [<span data-ttu-id="04e59-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="04e59-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
