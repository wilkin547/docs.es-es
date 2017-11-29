---
title: ICorDebugProcess2 Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2
helpviewer_keywords: ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca1a73874f6ca2f839639cbaf731a59721b2aede
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2-interface1"></a><span data-ttu-id="abee9-102">ICorDebugProcess2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="abee9-102">ICorDebugProcess2 Interface1</span></span>
<span data-ttu-id="abee9-103">Una extensión lógica de la interfaz ICorDebugProcess, que representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="abee9-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="abee9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="abee9-104">Methods</span></span>  
  
|<span data-ttu-id="abee9-105">Método</span><span class="sxs-lookup"><span data-stu-id="abee9-105">Method</span></span>|<span data-ttu-id="abee9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="abee9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="abee9-107">ClearUnmanagedBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="abee9-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="abee9-108">Quita un punto de interrupción en el desplazamiento especificado establecido por una llamada anterior a `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="abee9-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="abee9-109">GetDesiredNGENCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="abee9-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="abee9-110">Obtiene las marcas que se deben establecer para common language runtime (CLR) para cargar la imagen en el proceso que hace referencia esta `ICorDebugProcess2`.</span><span class="sxs-lookup"><span data-stu-id="abee9-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="abee9-111">GetReferenceValueFromGCHandle (método)</span><span class="sxs-lookup"><span data-stu-id="abee9-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="abee9-112">Obtiene un puntero de referencia al objeto administrado especificado que tiene una colección de elementos no utilizados controlar.</span><span class="sxs-lookup"><span data-stu-id="abee9-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="abee9-113">GetThreadForTaskID (método)</span><span class="sxs-lookup"><span data-stu-id="abee9-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="abee9-114">Obtiene el subproceso en el que está ejecutando la tarea con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="abee9-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="abee9-115">GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="abee9-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="abee9-116">Obtiene la versión de CLR en el que se ejecuta el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="abee9-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="abee9-117">SetDesiredNGENCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="abee9-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="abee9-118">Establece las marcas que son necesarias para el compilador de just-in-time (JIT) cargar una imagen en el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="abee9-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="abee9-119">SetUnmanagedBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="abee9-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="abee9-120">Establece un punto de interrupción no administrado en el desplazamiento de imagen nativa especificado.</span><span class="sxs-lookup"><span data-stu-id="abee9-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abee9-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="abee9-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abee9-122">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="abee9-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abee9-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abee9-123">Requirements</span></span>  
 <span data-ttu-id="abee9-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abee9-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abee9-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="abee9-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="abee9-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="abee9-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="abee9-127">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abee9-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abee9-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="abee9-128">See Also</span></span>  
 [<span data-ttu-id="abee9-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="abee9-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
