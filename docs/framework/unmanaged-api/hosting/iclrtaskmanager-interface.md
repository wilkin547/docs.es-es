---
title: ICLRTaskManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager
helpviewer_keywords:
- ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type:
- apiref
ms.openlocfilehash: e25a6a03a836b8b4964b8260c974c8e8d8d9998d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092184"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="bf9dd-102">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf9dd-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="bf9dd-103">Proporciona métodos que permiten al host solicitar explícitamente que el Common Language Runtime (CLR) cree una nueva tarea, obtenga la tarea que se está ejecutando actualmente y establezca el idioma geográfico y la referencia cultural de la tarea.</span><span class="sxs-lookup"><span data-stu-id="bf9dd-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf9dd-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="bf9dd-104">Methods</span></span>  
  
|<span data-ttu-id="bf9dd-105">Método</span><span class="sxs-lookup"><span data-stu-id="bf9dd-105">Method</span></span>|<span data-ttu-id="bf9dd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf9dd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf9dd-107">CreateTask (método)</span><span class="sxs-lookup"><span data-stu-id="bf9dd-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="bf9dd-108">Solicita explícitamente que CLR cree una nueva instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bf9dd-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="bf9dd-109">GetCurrentTask (método)</span><span class="sxs-lookup"><span data-stu-id="bf9dd-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="bf9dd-110">Obtiene la instancia de `ICLRTask` que representa la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="bf9dd-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="bf9dd-111">GetCurrentTaskType (método)</span><span class="sxs-lookup"><span data-stu-id="bf9dd-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="bf9dd-112">Obtiene el tipo de la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="bf9dd-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="bf9dd-113">SetLocale (método)</span><span class="sxs-lookup"><span data-stu-id="bf9dd-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="bf9dd-114">Notifica a CLR que el host ha modificado el identificador de configuración regional en la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="bf9dd-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="bf9dd-115">SetUILocale (método)</span><span class="sxs-lookup"><span data-stu-id="bf9dd-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="bf9dd-116">Notifica a la Common Language Runtime que el host ha modificado el identificador de configuración regional de la interfaz de usuario en la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="bf9dd-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf9dd-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf9dd-117">Remarks</span></span>  
 <span data-ttu-id="bf9dd-118">Cada tarea que se ejecuta en un entorno hospedado tiene representaciones tanto en el lado host (una instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) como en el lado de CLR (una instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="bf9dd-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="bf9dd-119">Tanto el host como el CLR pueden iniciar la creación de una tarea, pero la representación en el host debe estar asociada a una representación del lado del CLR correspondiente para garantizar una comunicación correcta entre el host y el CLR con respecto a la tarea.</span><span class="sxs-lookup"><span data-stu-id="bf9dd-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="bf9dd-120">Los dos objetos deben crearse y crearse instancias antes de que el código administrado pueda ejecutarse en un subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="bf9dd-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf9dd-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf9dd-121">Requirements</span></span>  
 <span data-ttu-id="bf9dd-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf9dd-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf9dd-123">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bf9dd-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bf9dd-124">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bf9dd-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf9dd-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf9dd-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf9dd-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf9dd-126">See also</span></span>

- [<span data-ttu-id="bf9dd-127">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf9dd-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="bf9dd-128">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf9dd-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="bf9dd-129">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf9dd-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="bf9dd-130">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="bf9dd-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
