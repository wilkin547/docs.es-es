---
description: 'Más información acerca de: ICLRTaskManager (interfaz)'
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
ms.openlocfilehash: 0ce3641042725bc2f3acb95933ccd7a5bbe3bc4d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789754"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="fc90e-103">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc90e-103">ICLRTaskManager Interface</span></span>

<span data-ttu-id="fc90e-104">Proporciona métodos que permiten al host solicitar explícitamente que el Common Language Runtime (CLR) cree una nueva tarea, obtenga la tarea que se está ejecutando actualmente y establezca el idioma geográfico y la referencia cultural de la tarea.</span><span class="sxs-lookup"><span data-stu-id="fc90e-104">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc90e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fc90e-105">Methods</span></span>  
  
|<span data-ttu-id="fc90e-106">Método</span><span class="sxs-lookup"><span data-stu-id="fc90e-106">Method</span></span>|<span data-ttu-id="fc90e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc90e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc90e-108">CreateTask (Método)</span><span class="sxs-lookup"><span data-stu-id="fc90e-108">CreateTask Method</span></span>](iclrtaskmanager-createtask-method.md)|<span data-ttu-id="fc90e-109">Solicita explícitamente que CLR cree una nueva instancia de [ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="fc90e-109">Requests explicitly that the CLR create a new [ICLRTask](iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="fc90e-110">Método GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="fc90e-110">GetCurrentTask Method</span></span>](iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="fc90e-111">Obtiene la `ICLRTask` instancia de que representa la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="fc90e-111">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="fc90e-112">Método GetCurrentTaskType</span><span class="sxs-lookup"><span data-stu-id="fc90e-112">GetCurrentTaskType Method</span></span>](iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="fc90e-113">Obtiene el tipo de la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="fc90e-113">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="fc90e-114">Método SetLocale</span><span class="sxs-lookup"><span data-stu-id="fc90e-114">SetLocale Method</span></span>](iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="fc90e-115">Notifica a CLR que el host ha modificado el identificador de configuración regional en la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="fc90e-115">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="fc90e-116">Método SetUILocale</span><span class="sxs-lookup"><span data-stu-id="fc90e-116">SetUILocale Method</span></span>](iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="fc90e-117">Notifica a la Common Language Runtime que el host ha modificado el identificador de configuración regional de la interfaz de usuario en la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="fc90e-117">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc90e-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fc90e-118">Remarks</span></span>  

 <span data-ttu-id="fc90e-119">Cada tarea que se ejecuta en un entorno hospedado tiene representaciones tanto en el lado host (una instancia de [IHostTask](ihosttask-interface.md)) como en el lado de CLR (una instancia de [ICLRTask](iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="fc90e-119">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](iclrtask-interface.md)).</span></span> <span data-ttu-id="fc90e-120">Tanto el host como el CLR pueden iniciar la creación de una tarea, pero la representación en el host debe estar asociada a una representación del lado del CLR correspondiente para garantizar una comunicación correcta entre el host y el CLR con respecto a la tarea.</span><span class="sxs-lookup"><span data-stu-id="fc90e-120">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="fc90e-121">Los dos objetos deben crearse y crearse instancias antes de que el código administrado pueda ejecutarse en un subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fc90e-121">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc90e-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc90e-122">Requirements</span></span>  

 <span data-ttu-id="fc90e-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc90e-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc90e-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fc90e-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc90e-125">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc90e-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc90e-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc90e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc90e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc90e-127">See also</span></span>

- [<span data-ttu-id="fc90e-128">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc90e-128">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="fc90e-129">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc90e-129">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="fc90e-130">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc90e-130">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="fc90e-131">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="fc90e-131">Hosting Interfaces</span></span>](hosting-interfaces.md)
