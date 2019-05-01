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
ms.openlocfilehash: 0ac28f28d4d284ba26fadd46e53ebeb8e5b5f3cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984157"
---
# <a name="waitoption-enumeration"></a><span data-ttu-id="f0403-102">WAIT_OPTION (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f0403-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="f0403-103">Contiene valores que indican que la acción de un host debe realizar si una operación solicitada por el common language runtime (CLR) bloquea.</span><span class="sxs-lookup"><span data-stu-id="f0403-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0403-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0403-104">Syntax</span></span>  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="f0403-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f0403-105">Members</span></span>  
  
|<span data-ttu-id="f0403-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f0403-106">Member</span></span>|<span data-ttu-id="f0403-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0403-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="f0403-108">Notifica al host que la tarea debe activarse si CLR llama a la [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="f0403-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="f0403-109">Notifica al host que debe suministrar mensajes en el subproceso del sistema operativo actual si se bloquea el subproceso.</span><span class="sxs-lookup"><span data-stu-id="f0403-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="f0403-110">El tiempo de ejecución especifica este valor solo en un <xref:System.Threading.ApartmentState.STA> subproceso.</span><span class="sxs-lookup"><span data-stu-id="f0403-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="f0403-111">Notifica al host que la solicitud de sincronización especificado no puede verse interrumpida por un host.</span><span class="sxs-lookup"><span data-stu-id="f0403-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="f0403-112">Es decir, el host no puede devolver `HOST_E_DEADLOCK`.</span><span class="sxs-lookup"><span data-stu-id="f0403-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0403-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f0403-113">Remarks</span></span>  
 <span data-ttu-id="f0403-114">El [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) y [SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) dos métodos toman un parámetro de este tipo.</span><span class="sxs-lookup"><span data-stu-id="f0403-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0403-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0403-115">Requirements</span></span>  
 <span data-ttu-id="f0403-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0403-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0403-117">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f0403-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0403-118">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f0403-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0403-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0403-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0403-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0403-120">See also</span></span>

- [<span data-ttu-id="f0403-121">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="f0403-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
