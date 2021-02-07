---
description: 'Más información acerca de: ICLRDebugManager (interfaz)'
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
ms.openlocfilehash: 4306e38b7c868561276d5b00e7730b6fcee46fd7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746033"
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="2caf9-103">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2caf9-103">ICLRDebugManager Interface</span></span>

<span data-ttu-id="2caf9-104">Proporciona métodos que permiten a un host asociar un conjunto de tareas con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="2caf9-104">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2caf9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2caf9-105">Methods</span></span>  
  
|<span data-ttu-id="2caf9-106">Método</span><span class="sxs-lookup"><span data-stu-id="2caf9-106">Method</span></span>|<span data-ttu-id="2caf9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2caf9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2caf9-108">Método BeginConnection</span><span class="sxs-lookup"><span data-stu-id="2caf9-108">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="2caf9-109">Establece una nueva conexión entre el host y el depurador para asociar las tareas con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="2caf9-109">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="2caf9-110">Método EndConnection</span><span class="sxs-lookup"><span data-stu-id="2caf9-110">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="2caf9-111">Quita la asociación entre una lista de tareas y un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="2caf9-111">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="2caf9-112">Método GetDacl</span><span class="sxs-lookup"><span data-stu-id="2caf9-112">GetDacl Method</span></span>](iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="2caf9-113">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="2caf9-113">This method is not implemented.</span></span>|  
|[<span data-ttu-id="2caf9-114">Método IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="2caf9-114">IsDebuggerAttached Method</span></span>](iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="2caf9-115">Obtiene un valor que indica si hay un depurador asociado al proceso.</span><span class="sxs-lookup"><span data-stu-id="2caf9-115">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="2caf9-116">Método SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="2caf9-116">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="2caf9-117">Asocia una lista de instancias de [ICLRTask](iclrtask-interface.md) con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="2caf9-117">Associates a list of [ICLRTask](iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="2caf9-118">Método SetDacl</span><span class="sxs-lookup"><span data-stu-id="2caf9-118">SetDacl Method</span></span>](iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="2caf9-119">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="2caf9-119">This method is not implemented.</span></span>|  
|[<span data-ttu-id="2caf9-120">Método SetSymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="2caf9-120">SetSymbolReadingPolicy Method</span></span>](iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="2caf9-121">Establece la Directiva para leer archivos de base de datos de programa (PDB).</span><span class="sxs-lookup"><span data-stu-id="2caf9-121">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="2caf9-122">La Directiva determina si la información sobre los números de línea y los archivos se incluye en las pilas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="2caf9-122">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2caf9-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2caf9-123">Remarks</span></span>  

 <span data-ttu-id="2caf9-124">En los escenarios de depuración, es posible que un host desee agrupar las tareas según su propia lógica de programación.</span><span class="sxs-lookup"><span data-stu-id="2caf9-124">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="2caf9-125">Por ejemplo, una agrupación permitiría a un desarrollador ver solo las tareas requeridas por las API del desarrollador, en lugar de ver todas las tareas que se ejecutan en el proceso.</span><span class="sxs-lookup"><span data-stu-id="2caf9-125">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="2caf9-126">`ICLRDebugManager` permite que el host implemente este tipo de agrupación.</span><span class="sxs-lookup"><span data-stu-id="2caf9-126">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2caf9-127">Tres `ICLRDebugManager` métodos, `BeginConnection` `SetConnectionTasks` y, `EndConnection` dependen unos de otros.</span><span class="sxs-lookup"><span data-stu-id="2caf9-127">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="2caf9-128">Se les debe llamar en el orden especificado para que funcionen según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="2caf9-128">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="2caf9-129">La agrupación, y los identificadores y nombres descriptivos que el host asigna a la agrupación, no tienen ningún significado para el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2caf9-129">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="2caf9-130">CLR simplemente pasa la información junto con el depurador.</span><span class="sxs-lookup"><span data-stu-id="2caf9-130">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2caf9-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2caf9-131">Requirements</span></span>  

 <span data-ttu-id="2caf9-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2caf9-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2caf9-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2caf9-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2caf9-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2caf9-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2caf9-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2caf9-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2caf9-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="2caf9-136">See also</span></span>

- [<span data-ttu-id="2caf9-137">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="2caf9-137">Hosting Interfaces</span></span>](hosting-interfaces.md)
