---
description: 'Más información acerca de: interfaz ICorDebugProcess2'
title: Interfaz ICorDebugProcess2
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
ms.openlocfilehash: 47e94ee8ee4f45e365fa9efe888cb706f8bb1dfd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746599"
---
# <a name="icordebugprocess2-interface"></a><span data-ttu-id="65570-103">Interfaz ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="65570-103">ICorDebugProcess2 Interface</span></span>

<span data-ttu-id="65570-104">Extensión lógica de la interfaz ICorDebugProcess, que representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="65570-104">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65570-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="65570-105">Methods</span></span>  
  
|<span data-ttu-id="65570-106">Método</span><span class="sxs-lookup"><span data-stu-id="65570-106">Method</span></span>|<span data-ttu-id="65570-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="65570-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65570-108">Método ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="65570-108">ClearUnmanagedBreakpoint Method</span></span>](icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="65570-109">Quita un punto de interrupción en el desplazamiento especificado establecido por una llamada anterior a `ICorDebugProcess2::SetUnmanagedBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="65570-109">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="65570-110">Método GetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="65570-110">GetDesiredNGENCompilerFlags Method</span></span>](icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="65570-111">Obtiene las marcas que se deben establecer para el Common Language Runtime (CLR) para cargar la imagen en el proceso al que hace referencia `ICorDebugProcess2` .</span><span class="sxs-lookup"><span data-stu-id="65570-111">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="65570-112">Método GetReferenceValueFromGCHandle</span><span class="sxs-lookup"><span data-stu-id="65570-112">GetReferenceValueFromGCHandle Method</span></span>](icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="65570-113">Obtiene un puntero de referencia al objeto administrado especificado que tiene un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="65570-113">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="65570-114">Método GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="65570-114">GetThreadForTaskID Method</span></span>](icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="65570-115">Obtiene el subproceso en el que se está ejecutando la tarea con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="65570-115">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="65570-116">Método GetVersion</span><span class="sxs-lookup"><span data-stu-id="65570-116">GetVersion Method</span></span>](icordebugprocess2-getversion-method.md)|<span data-ttu-id="65570-117">Obtiene la versión de CLR en la que se está ejecutando el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="65570-117">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="65570-118">Método SetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="65570-118">SetDesiredNGENCompilerFlags Method</span></span>](icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="65570-119">Establece las marcas necesarias para que el compilador Just-in-Time (JIT) cargue una imagen en el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="65570-119">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="65570-120">Método SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="65570-120">SetUnmanagedBreakpoint Method</span></span>](icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="65570-121">Establece un punto de interrupción no administrado en el desplazamiento de imagen nativo especificado.</span><span class="sxs-lookup"><span data-stu-id="65570-121">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65570-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="65570-122">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="65570-123">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="65570-123">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65570-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65570-124">Requirements</span></span>  

 <span data-ttu-id="65570-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65570-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65570-126">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65570-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65570-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65570-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65570-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65570-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65570-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="65570-129">See also</span></span>

- [<span data-ttu-id="65570-130">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="65570-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
