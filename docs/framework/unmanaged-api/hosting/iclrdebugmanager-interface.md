---
title: ICLRDebugManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 515eb0633c82c3e1386487d1866de79c9898c9cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654612"
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="16b78-102">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="16b78-102">ICLRDebugManager Interface</span></span>
<span data-ttu-id="16b78-103">Proporciona métodos que permiten a un host asociar un conjunto de tareas con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="16b78-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="16b78-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="16b78-104">Methods</span></span>  
  
|<span data-ttu-id="16b78-105">Método</span><span class="sxs-lookup"><span data-stu-id="16b78-105">Method</span></span>|<span data-ttu-id="16b78-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="16b78-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="16b78-107">BeginConnection (método)</span><span class="sxs-lookup"><span data-stu-id="16b78-107">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="16b78-108">Establece una nueva conexión entre el host y el depurador para asociar tareas a un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="16b78-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="16b78-109">EndConnection (método)</span><span class="sxs-lookup"><span data-stu-id="16b78-109">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="16b78-110">Quita la asociación entre una lista de tareas y un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="16b78-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="16b78-111">GetDacl (método)</span><span class="sxs-lookup"><span data-stu-id="16b78-111">GetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="16b78-112">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="16b78-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="16b78-113">IsDebuggerAttached (método)</span><span class="sxs-lookup"><span data-stu-id="16b78-113">IsDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="16b78-114">Obtiene un valor que indica si hay un depurador asociado al proceso.</span><span class="sxs-lookup"><span data-stu-id="16b78-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="16b78-115">SetConnectionTasks (método)</span><span class="sxs-lookup"><span data-stu-id="16b78-115">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="16b78-116">Asocia una lista de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancias con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="16b78-116">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="16b78-117">SetDacl (método)</span><span class="sxs-lookup"><span data-stu-id="16b78-117">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="16b78-118">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="16b78-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="16b78-119">SetSymbolReadingPolicy (método)</span><span class="sxs-lookup"><span data-stu-id="16b78-119">SetSymbolReadingPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="16b78-120">Establece la directiva para leer los archivos de programa (PDB) de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="16b78-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="16b78-121">La directiva determina si se incluye información sobre archivos y números de línea en las pilas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="16b78-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16b78-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16b78-122">Remarks</span></span>  
 <span data-ttu-id="16b78-123">En escenarios de depuración, un host podría desear agrupar las tareas según su propia lógica de programación.</span><span class="sxs-lookup"><span data-stu-id="16b78-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="16b78-124">Por ejemplo, una agrupación permitiría que un desarrollador ver solo las tareas necesarias de las API del desarrollador, en lugar de ver todas las tareas que se ejecutan en el proceso.</span><span class="sxs-lookup"><span data-stu-id="16b78-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="16b78-125">`ICLRDebugManager` permite al host implementar este tipo de agrupación.</span><span class="sxs-lookup"><span data-stu-id="16b78-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="16b78-126">Tres `ICLRDebugManager` métodos, `BeginConnection`, `SetConnectionTasks` y `EndConnection`, son dependientes entre sí.</span><span class="sxs-lookup"><span data-stu-id="16b78-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="16b78-127">Se debe llamar en el orden especificado para que funcione según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="16b78-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="16b78-128">La agrupación y los identificadores y nombres descriptivos que el host se asigna a la agrupación, no tienen ningún significado para common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="16b78-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="16b78-129">El CLR simplemente pasa la información al depurador.</span><span class="sxs-lookup"><span data-stu-id="16b78-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16b78-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16b78-130">Requirements</span></span>  
 <span data-ttu-id="16b78-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16b78-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16b78-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="16b78-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16b78-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="16b78-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16b78-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16b78-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b78-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="16b78-135">See also</span></span>
- [<span data-ttu-id="16b78-136">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="16b78-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
