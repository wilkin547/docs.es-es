---
title: ICorDebugProcess::SetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
ms.openlocfilehash: c9e403dc8cbb75a1e93c426a9e0b3a2083f1f10e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210467"
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="357be-102">ICorDebugProcess::SetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="357be-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="357be-103">Establece el contexto para el subproceso dado en este proceso.</span><span class="sxs-lookup"><span data-stu-id="357be-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="357be-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="357be-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="357be-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="357be-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="357be-106">de IDENTIFICADOR del subproceso para el que se va a establecer el contexto.</span><span class="sxs-lookup"><span data-stu-id="357be-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="357be-107">[in] Tamaño de la matriz `context`.</span><span class="sxs-lookup"><span data-stu-id="357be-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="357be-108">de Matriz de bytes que describen el contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="357be-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="357be-109">El contexto especifica la arquitectura del procesador en el que se ejecuta el subproceso.</span><span class="sxs-lookup"><span data-stu-id="357be-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="357be-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="357be-110">Remarks</span></span>  
 <span data-ttu-id="357be-111">El depurador debe llamar a este método en lugar de a la función de Win32 `SetThreadContext` , ya que el subproceso puede estar realmente en un estado "secuestrado", en el que su contexto ha cambiado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="357be-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="357be-112">Este método solo se debe usar cuando un subproceso está en código nativo.</span><span class="sxs-lookup"><span data-stu-id="357be-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="357be-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) para subprocesos en código administrado.</span><span class="sxs-lookup"><span data-stu-id="357be-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="357be-114">Nunca debe modificar el contexto de un subproceso durante un evento de depuración fuera de banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="357be-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="357be-115">Los datos pasados deben ser una estructura de contexto para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="357be-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="357be-116">Este método puede dañar el tiempo de ejecución si se usa de forma incorrecta.</span><span class="sxs-lookup"><span data-stu-id="357be-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="357be-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="357be-117">Requirements</span></span>  
 <span data-ttu-id="357be-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="357be-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="357be-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="357be-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="357be-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="357be-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="357be-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="357be-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
