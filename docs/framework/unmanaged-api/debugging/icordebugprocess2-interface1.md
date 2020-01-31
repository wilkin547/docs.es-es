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
ms.openlocfilehash: 1ef6af11851acbe0f7e9469c9432ff09f9228608
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792507"
---
# <a name="icordebugprocess2-interface"></a><span data-ttu-id="f4cf5-102">Interfaz ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="f4cf5-102">ICorDebugProcess2 Interface</span></span>
<span data-ttu-id="f4cf5-103">Extensión lógica de la interfaz ICorDebugProcess, que representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4cf5-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f4cf5-104">Methods</span></span>  
  
|<span data-ttu-id="f4cf5-105">Método</span><span class="sxs-lookup"><span data-stu-id="f4cf5-105">Method</span></span>|<span data-ttu-id="f4cf5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4cf5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4cf5-107">ClearUnmanagedBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="f4cf5-107">ClearUnmanagedBreakpoint Method</span></span>](icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="f4cf5-108">Quita un punto de interrupción en el desplazamiento especificado establecido por una llamada anterior a `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="f4cf5-109">GetDesiredNGENCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="f4cf5-109">GetDesiredNGENCompilerFlags Method</span></span>](icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="f4cf5-110">Obtiene las marcas que se deben establecer para el Common Language Runtime (CLR) para cargar la imagen en el proceso al que hace referencia esta `ICorDebugProcess2`.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="f4cf5-111">GetReferenceValueFromGCHandle (método)</span><span class="sxs-lookup"><span data-stu-id="f4cf5-111">GetReferenceValueFromGCHandle Method</span></span>](icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="f4cf5-112">Obtiene un puntero de referencia al objeto administrado especificado que tiene un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="f4cf5-113">GetThreadForTaskID (método)</span><span class="sxs-lookup"><span data-stu-id="f4cf5-113">GetThreadForTaskID Method</span></span>](icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="f4cf5-114">Obtiene el subproceso en el que se está ejecutando la tarea con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="f4cf5-115">GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="f4cf5-115">GetVersion Method</span></span>](icordebugprocess2-getversion-method.md)|<span data-ttu-id="f4cf5-116">Obtiene la versión de CLR en la que se está ejecutando el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="f4cf5-117">SetDesiredNGENCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="f4cf5-117">SetDesiredNGENCompilerFlags Method</span></span>](icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="f4cf5-118">Establece las marcas necesarias para que el compilador Just-in-Time (JIT) cargue una imagen en el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="f4cf5-119">SetUnmanagedBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="f4cf5-119">SetUnmanagedBreakpoint Method</span></span>](icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="f4cf5-120">Establece un punto de interrupción no administrado en el desplazamiento de imagen nativo especificado.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4cf5-121">Notas</span><span class="sxs-lookup"><span data-stu-id="f4cf5-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f4cf5-122">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f4cf5-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4cf5-123">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f4cf5-123">Requirements</span></span>  
 <span data-ttu-id="f4cf5-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4cf5-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4cf5-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4cf5-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4cf5-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4cf5-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4cf5-127">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4cf5-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4cf5-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4cf5-128">See also</span></span>

- [<span data-ttu-id="f4cf5-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f4cf5-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
