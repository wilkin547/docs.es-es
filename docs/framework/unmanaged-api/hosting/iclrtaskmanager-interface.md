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
ms.openlocfilehash: 1170b29c01275b108a6ccdf6e324c96d97c10c82
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732455"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="320c1-102">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="320c1-102">ICLRTaskManager Interface</span></span>

<span data-ttu-id="320c1-103">Proporciona métodos que permiten al host solicitar explícitamente que el Common Language Runtime (CLR) cree una nueva tarea, obtenga la tarea que se está ejecutando actualmente y establezca el idioma geográfico y la referencia cultural de la tarea.</span><span class="sxs-lookup"><span data-stu-id="320c1-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="320c1-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="320c1-104">Methods</span></span>  
  
|<span data-ttu-id="320c1-105">Método</span><span class="sxs-lookup"><span data-stu-id="320c1-105">Method</span></span>|<span data-ttu-id="320c1-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="320c1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="320c1-107">CreateTask (Método)</span><span class="sxs-lookup"><span data-stu-id="320c1-107">CreateTask Method</span></span>](iclrtaskmanager-createtask-method.md)|<span data-ttu-id="320c1-108">Solicita explícitamente que CLR cree una nueva instancia de [ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="320c1-108">Requests explicitly that the CLR create a new [ICLRTask](iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="320c1-109">Método GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="320c1-109">GetCurrentTask Method</span></span>](iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="320c1-110">Obtiene la `ICLRTask` instancia de que representa la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="320c1-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="320c1-111">Método GetCurrentTaskType</span><span class="sxs-lookup"><span data-stu-id="320c1-111">GetCurrentTaskType Method</span></span>](iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="320c1-112">Obtiene el tipo de la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="320c1-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="320c1-113">Método SetLocale</span><span class="sxs-lookup"><span data-stu-id="320c1-113">SetLocale Method</span></span>](iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="320c1-114">Notifica a CLR que el host ha modificado el identificador de configuración regional en la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="320c1-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="320c1-115">Método SetUILocale</span><span class="sxs-lookup"><span data-stu-id="320c1-115">SetUILocale Method</span></span>](iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="320c1-116">Notifica a la Common Language Runtime que el host ha modificado el identificador de configuración regional de la interfaz de usuario en la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="320c1-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="320c1-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="320c1-117">Remarks</span></span>  

 <span data-ttu-id="320c1-118">Cada tarea que se ejecuta en un entorno hospedado tiene representaciones tanto en el lado host (una instancia de [IHostTask](ihosttask-interface.md)) como en el lado de CLR (una instancia de [ICLRTask](iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="320c1-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](iclrtask-interface.md)).</span></span> <span data-ttu-id="320c1-119">Tanto el host como el CLR pueden iniciar la creación de una tarea, pero la representación en el host debe estar asociada a una representación del lado del CLR correspondiente para garantizar una comunicación correcta entre el host y el CLR con respecto a la tarea.</span><span class="sxs-lookup"><span data-stu-id="320c1-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="320c1-120">Los dos objetos deben crearse y crearse instancias antes de que el código administrado pueda ejecutarse en un subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="320c1-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="320c1-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="320c1-121">Requirements</span></span>  

 <span data-ttu-id="320c1-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="320c1-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="320c1-123">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="320c1-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="320c1-124">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="320c1-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="320c1-125">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="320c1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="320c1-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="320c1-126">See also</span></span>

- [<span data-ttu-id="320c1-127">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="320c1-127">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="320c1-128">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="320c1-128">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="320c1-129">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="320c1-129">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="320c1-130">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="320c1-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
