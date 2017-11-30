---
title: "ICorDebugProcess::SetThreadContext (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.SetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 70368602672e06dc3a5aaf4f2f4bc7632c5a9a79
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="d4aa3-102">ICorDebugProcess::SetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="d4aa3-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="d4aa3-103">Establece el contexto para el subproceso especificado en este proceso.</span><span class="sxs-lookup"><span data-stu-id="d4aa3-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4aa3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4aa3-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4aa3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4aa3-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="d4aa3-106">[in] El identificador del subproceso para el que se va a establecer el contexto.</span><span class="sxs-lookup"><span data-stu-id="d4aa3-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="d4aa3-107">[in] Tamaño de la matriz `context`.</span><span class="sxs-lookup"><span data-stu-id="d4aa3-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="d4aa3-108">[in] Una matriz de bytes que describen el contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="d4aa3-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="d4aa3-109">El contexto especifica la arquitectura del procesador en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="d4aa3-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4aa3-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d4aa3-110">Remarks</span></span>  
 <span data-ttu-id="d4aa3-111">El depurador debe llamar a este método en lugar de Win32 `SetThreadContext` funciona, ya que el subproceso esté realmente en un estado de "secuestro", en el que se ha cambiado temporalmente su contexto.</span><span class="sxs-lookup"><span data-stu-id="d4aa3-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="d4aa3-112">Este método debe utilizarse únicamente cuando un subproceso está en código nativo.</span><span class="sxs-lookup"><span data-stu-id="d4aa3-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="d4aa3-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) para subprocesos en código administrado.</span><span class="sxs-lookup"><span data-stu-id="d4aa3-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="d4aa3-114">Nunca es necesario modificar el contexto de un subproceso durante un evento de depuración fuera de banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="d4aa3-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="d4aa3-115">Los datos pasados deben ser una estructura de contexto para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="d4aa3-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="d4aa3-116">Este método puede dañar el tiempo de ejecución si se utiliza incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="d4aa3-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4aa3-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4aa3-117">Requirements</span></span>  
 <span data-ttu-id="d4aa3-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4aa3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4aa3-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4aa3-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4aa3-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4aa3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4aa3-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4aa3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
