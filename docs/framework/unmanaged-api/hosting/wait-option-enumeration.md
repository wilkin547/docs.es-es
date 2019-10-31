---
title: WAIT_OPTION (Enumeración)
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
ms.openlocfilehash: 9ecfb551b55551e5f6cc7e7e9ffb55e5a96259ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141517"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="84aeb-102">WAIT_OPTION (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="84aeb-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="84aeb-103">Contiene valores que indican la acción que debe realizar un host si una operación solicitada por los bloques de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="84aeb-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84aeb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84aeb-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="84aeb-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="84aeb-105">Members</span></span>  
  
|<span data-ttu-id="84aeb-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="84aeb-106">Member</span></span>|<span data-ttu-id="84aeb-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="84aeb-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="84aeb-108">Notifica al host que la tarea se debe reactivar si CLR llama al método [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="84aeb-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="84aeb-109">Notifica al host que debe bombear los mensajes en el subproceso del sistema operativo actual si el subproceso se bloquea.</span><span class="sxs-lookup"><span data-stu-id="84aeb-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="84aeb-110">El tiempo de ejecución especifica este valor solo en un subproceso de <xref:System.Threading.ApartmentState.STA>.</span><span class="sxs-lookup"><span data-stu-id="84aeb-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="84aeb-111">Notifica al host que un host no puede interrumpir la solicitud de sincronización especificada.</span><span class="sxs-lookup"><span data-stu-id="84aeb-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="84aeb-112">Es decir, el host no puede devolver `HOST_E_DEADLOCK`.</span><span class="sxs-lookup"><span data-stu-id="84aeb-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84aeb-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="84aeb-113">Remarks</span></span>  
 <span data-ttu-id="84aeb-114">Los métodos [IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) y [IHostTaskManager:: switchtotask (](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) toman un parámetro de este tipo.</span><span class="sxs-lookup"><span data-stu-id="84aeb-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84aeb-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84aeb-115">Requirements</span></span>  
 <span data-ttu-id="84aeb-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84aeb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84aeb-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="84aeb-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84aeb-118">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="84aeb-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84aeb-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84aeb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84aeb-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="84aeb-120">See also</span></span>

- [<span data-ttu-id="84aeb-121">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="84aeb-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
