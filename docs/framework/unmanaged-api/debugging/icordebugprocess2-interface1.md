---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49b3bb51f307093ea1cc8cc45064d5c405974822
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948855"
---
# <a name="icordebugprocess2-interface"></a><span data-ttu-id="8747c-102">Interfaz ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="8747c-102">ICorDebugProcess2 Interface</span></span>
<span data-ttu-id="8747c-103">Una extensión lógica de la interfaz ICorDebugProcess, que representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="8747c-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8747c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8747c-104">Methods</span></span>  
  
|<span data-ttu-id="8747c-105">Método</span><span class="sxs-lookup"><span data-stu-id="8747c-105">Method</span></span>|<span data-ttu-id="8747c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8747c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8747c-107">ClearUnmanagedBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="8747c-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="8747c-108">Quita un punto de interrupción en el desplazamiento especificado que se ha establecido mediante una llamada anterior a `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="8747c-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="8747c-109">GetDesiredNGENCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="8747c-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="8747c-110">Obtiene las marcas que se deben establecer para common language runtime (CLR) para cargar la imagen en el proceso que hace referencia esta `ICorDebugProcess2`.</span><span class="sxs-lookup"><span data-stu-id="8747c-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="8747c-111">GetReferenceValueFromGCHandle (método)</span><span class="sxs-lookup"><span data-stu-id="8747c-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="8747c-112">Obtiene un puntero de referencia al objeto administrado especificado que tiene una colección de elementos no utilizados de identificador.</span><span class="sxs-lookup"><span data-stu-id="8747c-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="8747c-113">GetThreadForTaskID (método)</span><span class="sxs-lookup"><span data-stu-id="8747c-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="8747c-114">Obtiene el subproceso en el que se ejecuta la tarea con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="8747c-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="8747c-115">GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="8747c-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="8747c-116">Obtiene la versión de CLR en el que se está ejecutando el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="8747c-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="8747c-117">SetDesiredNGENCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="8747c-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="8747c-118">Establece las marcas que son necesarias para el compilador de just-in-time (JIT) cargar una imagen en el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="8747c-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="8747c-119">SetUnmanagedBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="8747c-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="8747c-120">Establece un punto de interrupción no administrado en el desplazamiento de la imagen nativa especificada.</span><span class="sxs-lookup"><span data-stu-id="8747c-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8747c-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8747c-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8747c-122">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="8747c-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8747c-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8747c-123">Requirements</span></span>  
 <span data-ttu-id="8747c-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8747c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8747c-125">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8747c-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8747c-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8747c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8747c-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8747c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8747c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8747c-128">See also</span></span>

- [<span data-ttu-id="8747c-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8747c-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
