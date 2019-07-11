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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eda866c1a1f1f69f0d042ccfde3dfad293df9b37
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776509"
---
# <a name="waitoption-enumeration"></a><span data-ttu-id="2a747-102">WAIT_OPTION (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="2a747-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="2a747-103">Contiene valores que indican que la acción de un host debe realizar si una operación solicitada por el common language runtime (CLR) bloquea.</span><span class="sxs-lookup"><span data-stu-id="2a747-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a747-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a747-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="2a747-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2a747-105">Members</span></span>  
  
|<span data-ttu-id="2a747-106">Member</span><span class="sxs-lookup"><span data-stu-id="2a747-106">Member</span></span>|<span data-ttu-id="2a747-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2a747-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="2a747-108">Notifica al host que la tarea debe activarse si CLR llama a la [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="2a747-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="2a747-109">Notifica al host que debe suministrar mensajes en el subproceso del sistema operativo actual si se bloquea el subproceso.</span><span class="sxs-lookup"><span data-stu-id="2a747-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="2a747-110">El tiempo de ejecución especifica este valor solo en un <xref:System.Threading.ApartmentState.STA> subproceso.</span><span class="sxs-lookup"><span data-stu-id="2a747-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="2a747-111">Notifica al host que la solicitud de sincronización especificado no puede verse interrumpida por un host.</span><span class="sxs-lookup"><span data-stu-id="2a747-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="2a747-112">Es decir, el host no puede devolver `HOST_E_DEADLOCK`.</span><span class="sxs-lookup"><span data-stu-id="2a747-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a747-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a747-113">Remarks</span></span>  
 <span data-ttu-id="2a747-114">El [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) y [SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) dos métodos toman un parámetro de este tipo.</span><span class="sxs-lookup"><span data-stu-id="2a747-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a747-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a747-115">Requirements</span></span>  
 <span data-ttu-id="2a747-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a747-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a747-117">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2a747-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a747-118">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a747-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a747-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a747-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a747-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a747-120">See also</span></span>

- [<span data-ttu-id="2a747-121">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="2a747-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
