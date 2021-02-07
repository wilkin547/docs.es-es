---
description: 'Más información acerca de: enumeración WAIT_OPTION'
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
ms.openlocfilehash: 1d651909e0f62f2db7478a6e0b37139d1f953196
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679152"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="e37a3-103">WAIT_OPTION (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e37a3-103">WAIT_OPTION Enumeration</span></span>

<span data-ttu-id="e37a3-104">Contiene valores que indican la acción que debe realizar un host si una operación solicitada por los bloques de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e37a3-104">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e37a3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e37a3-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="e37a3-106">Members</span><span class="sxs-lookup"><span data-stu-id="e37a3-106">Members</span></span>  
  
|<span data-ttu-id="e37a3-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="e37a3-107">Member</span></span>|<span data-ttu-id="e37a3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e37a3-108">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="e37a3-109">Notifica al host que la tarea se debe reactivar si CLR llama al método [IHostTask:: Alert](ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e37a3-109">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="e37a3-110">Notifica al host que debe bombear los mensajes en el subproceso del sistema operativo actual si el subproceso se bloquea.</span><span class="sxs-lookup"><span data-stu-id="e37a3-110">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="e37a3-111">El tiempo de ejecución especifica este valor solo en un <xref:System.Threading.ApartmentState.STA> subproceso.</span><span class="sxs-lookup"><span data-stu-id="e37a3-111">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="e37a3-112">Notifica al host que un host no puede interrumpir la solicitud de sincronización especificada.</span><span class="sxs-lookup"><span data-stu-id="e37a3-112">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="e37a3-113">Es decir, el host no puede devolver `HOST_E_DEADLOCK` .</span><span class="sxs-lookup"><span data-stu-id="e37a3-113">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e37a3-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e37a3-114">Remarks</span></span>  

 <span data-ttu-id="e37a3-115">Los métodos [IHostTaskManager:: Sleep](ihosttaskmanager-sleep-method.md) y [IHostTaskManager:: switchtotask (](ihosttaskmanager-switchtotask-method.md) toman un parámetro de este tipo.</span><span class="sxs-lookup"><span data-stu-id="e37a3-115">The [IHostTaskManager::Sleep](ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e37a3-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e37a3-116">Requirements</span></span>  

 <span data-ttu-id="e37a3-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e37a3-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e37a3-118">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e37a3-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e37a3-119">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e37a3-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e37a3-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e37a3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e37a3-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e37a3-121">See also</span></span>

- [<span data-ttu-id="e37a3-122">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="e37a3-122">Hosting Enumerations</span></span>](hosting-enumerations.md)
