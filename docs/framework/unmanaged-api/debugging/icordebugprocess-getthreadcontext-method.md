---
title: "ICorDebugProcess::GetThreadContext (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1e45d101db946747463ba4200bc5dd3b95d21391
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="a53c8-102">ICorDebugProcess::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="a53c8-102">ICorDebugProcess::GetThreadContext Method</span></span>
<span data-ttu-id="a53c8-103">Obtiene el contexto para el subproceso determinado en este proceso.</span><span class="sxs-lookup"><span data-stu-id="a53c8-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a53c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a53c8-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a53c8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a53c8-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="a53c8-106">[in] El identificador del subproceso para el que se va a recuperar el contexto.</span><span class="sxs-lookup"><span data-stu-id="a53c8-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="a53c8-107">[in] Tamaño de la matriz `context`.</span><span class="sxs-lookup"><span data-stu-id="a53c8-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="a53c8-108">[entrada, salida] Una matriz de bytes que describen el contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="a53c8-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="a53c8-109">El contexto especifica la arquitectura del procesador en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="a53c8-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a53c8-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a53c8-110">Remarks</span></span>  
 <span data-ttu-id="a53c8-111">El depurador debe llamar a este método en lugar de Win32 `GetThreadContext` método, porque el subproceso esté realmente en un estado de "secuestro", en el que se ha cambiado temporalmente su contexto.</span><span class="sxs-lookup"><span data-stu-id="a53c8-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="a53c8-112">Este método debe utilizarse únicamente cuando un subproceso está en código nativo.</span><span class="sxs-lookup"><span data-stu-id="a53c8-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="a53c8-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) para subprocesos en código administrado.</span><span class="sxs-lookup"><span data-stu-id="a53c8-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="a53c8-114">Los datos devueltos están una estructura de contexto para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="a53c8-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="a53c8-115">Al igual que con Win32 `GetThreadContext` método, el llamador debe inicializar el `context` parámetro antes de llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="a53c8-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a53c8-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a53c8-116">Requirements</span></span>  
 <span data-ttu-id="a53c8-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a53c8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a53c8-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a53c8-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a53c8-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a53c8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a53c8-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a53c8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
