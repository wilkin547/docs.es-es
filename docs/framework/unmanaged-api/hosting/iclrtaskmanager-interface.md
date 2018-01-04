---
title: ICLRTaskManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager
helpviewer_keywords: ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 342d7b82802fcfbe9e179d85d6d692205f19e382
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="0d627-102">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d627-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="0d627-103">Proporciona métodos que permiten al host solicitar explícitamente que common language runtime (CLR) crean una nueva tarea, obtención la tarea que se está ejecuta actualmente y establecer el idioma geográfico y la referencia cultural para la tarea.</span><span class="sxs-lookup"><span data-stu-id="0d627-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d627-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0d627-104">Methods</span></span>  
  
|<span data-ttu-id="0d627-105">Método</span><span class="sxs-lookup"><span data-stu-id="0d627-105">Method</span></span>|<span data-ttu-id="0d627-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d627-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d627-107">CreateTask (método)</span><span class="sxs-lookup"><span data-stu-id="0d627-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="0d627-108">Solicita explícitamente que CLR cree una nueva [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="0d627-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="0d627-109">GetCurrentTask (método)</span><span class="sxs-lookup"><span data-stu-id="0d627-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="0d627-110">Obtiene el `ICLRTask` instancia que representa la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="0d627-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="0d627-111">GetCurrentTaskType (método)</span><span class="sxs-lookup"><span data-stu-id="0d627-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="0d627-112">Obtiene el tipo de la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="0d627-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="0d627-113">SetLocale (método)</span><span class="sxs-lookup"><span data-stu-id="0d627-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="0d627-114">Notifica a CLR que el host ha modificado el identificador de configuración regional en la tarea que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="0d627-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="0d627-115">SetUILocale (método)</span><span class="sxs-lookup"><span data-stu-id="0d627-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="0d627-116">Notifica a common language runtime que el host ha modificado el identificador de configuración regional de la interfaz de usuario en la tarea que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="0d627-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d627-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0d627-117">Remarks</span></span>  
 <span data-ttu-id="0d627-118">Cada tarea que se ejecuta en un entorno hospedado tiene representaciones tanto en el lado del host (una instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) y en el lado CLR (una instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="0d627-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="0d627-119">El host o el CLR puede iniciar la creación de una tarea, pero la representación del lado del host debe estar asociada con una representación de lado de CLR correspondiente para garantizar una comunicación correcta entre el host y CLR con respecto a la tarea.</span><span class="sxs-lookup"><span data-stu-id="0d627-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="0d627-120">Los dos objetos deben ser creados y crea una instancia antes de que el código administrado puede ejecutar en un subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0d627-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d627-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d627-121">Requirements</span></span>  
 <span data-ttu-id="0d627-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d627-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d627-123">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d627-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d627-124">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d627-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d627-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d627-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d627-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d627-126">See Also</span></span>  
 [<span data-ttu-id="0d627-127">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d627-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="0d627-128">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d627-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="0d627-129">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d627-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="0d627-130">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="0d627-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
