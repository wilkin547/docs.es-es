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
ms.openlocfilehash: 3836bd349423670a19a19dda67eba75419507a29
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724297"
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="65749-102">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="65749-102">ICLRDebugManager Interface</span></span>

<span data-ttu-id="65749-103">Proporciona métodos que permiten a un host asociar un conjunto de tareas con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="65749-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65749-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="65749-104">Methods</span></span>  
  
|<span data-ttu-id="65749-105">Método</span><span class="sxs-lookup"><span data-stu-id="65749-105">Method</span></span>|<span data-ttu-id="65749-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="65749-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65749-107">Método BeginConnection</span><span class="sxs-lookup"><span data-stu-id="65749-107">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="65749-108">Establece una nueva conexión entre el host y el depurador para asociar las tareas con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="65749-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="65749-109">Método EndConnection</span><span class="sxs-lookup"><span data-stu-id="65749-109">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="65749-110">Quita la asociación entre una lista de tareas y un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="65749-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="65749-111">Método GetDacl</span><span class="sxs-lookup"><span data-stu-id="65749-111">GetDacl Method</span></span>](iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="65749-112">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="65749-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="65749-113">Método IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="65749-113">IsDebuggerAttached Method</span></span>](iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="65749-114">Obtiene un valor que indica si hay un depurador asociado al proceso.</span><span class="sxs-lookup"><span data-stu-id="65749-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="65749-115">Método SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="65749-115">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="65749-116">Asocia una lista de instancias de [ICLRTask](iclrtask-interface.md) con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="65749-116">Associates a list of [ICLRTask](iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="65749-117">Método SetDacl</span><span class="sxs-lookup"><span data-stu-id="65749-117">SetDacl Method</span></span>](iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="65749-118">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="65749-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="65749-119">Método SetSymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="65749-119">SetSymbolReadingPolicy Method</span></span>](iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="65749-120">Establece la Directiva para leer archivos de base de datos de programa (PDB).</span><span class="sxs-lookup"><span data-stu-id="65749-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="65749-121">La Directiva determina si la información sobre los números de línea y los archivos se incluye en las pilas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="65749-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65749-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="65749-122">Remarks</span></span>  

 <span data-ttu-id="65749-123">En los escenarios de depuración, es posible que un host desee agrupar las tareas según su propia lógica de programación.</span><span class="sxs-lookup"><span data-stu-id="65749-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="65749-124">Por ejemplo, una agrupación permitiría a un desarrollador ver solo las tareas requeridas por las API del desarrollador, en lugar de ver todas las tareas que se ejecutan en el proceso.</span><span class="sxs-lookup"><span data-stu-id="65749-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="65749-125">`ICLRDebugManager` permite que el host implemente este tipo de agrupación.</span><span class="sxs-lookup"><span data-stu-id="65749-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="65749-126">Tres `ICLRDebugManager` métodos, `BeginConnection` `SetConnectionTasks` y, `EndConnection` dependen unos de otros.</span><span class="sxs-lookup"><span data-stu-id="65749-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="65749-127">Se les debe llamar en el orden especificado para que funcionen según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="65749-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="65749-128">La agrupación, y los identificadores y nombres descriptivos que el host asigna a la agrupación, no tienen ningún significado para el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="65749-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="65749-129">CLR simplemente pasa la información junto con el depurador.</span><span class="sxs-lookup"><span data-stu-id="65749-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65749-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65749-130">Requirements</span></span>  

 <span data-ttu-id="65749-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65749-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65749-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="65749-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65749-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="65749-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65749-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65749-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65749-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65749-135">See also</span></span>

- [<span data-ttu-id="65749-136">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="65749-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
