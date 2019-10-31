---
title: ICorDebugProcess::GetThreadContext (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: c6def272ecc7bd2b6e946e2c9623f0b60587d317
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128809"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="73f2b-102">ICorDebugProcess::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="73f2b-102">ICorDebugProcess::GetThreadContext Method</span></span>
<span data-ttu-id="73f2b-103">Obtiene el contexto para el subproceso dado en este proceso.</span><span class="sxs-lookup"><span data-stu-id="73f2b-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73f2b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73f2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73f2b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73f2b-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="73f2b-106">de IDENTIFICADOR del subproceso para el que se va a recuperar el contexto.</span><span class="sxs-lookup"><span data-stu-id="73f2b-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="73f2b-107">[in] Tamaño de la matriz `context`.</span><span class="sxs-lookup"><span data-stu-id="73f2b-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="73f2b-108">[in, out] Matriz de bytes que describen el contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="73f2b-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="73f2b-109">El contexto especifica la arquitectura del procesador en el que se ejecuta el subproceso.</span><span class="sxs-lookup"><span data-stu-id="73f2b-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73f2b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73f2b-110">Remarks</span></span>  
 <span data-ttu-id="73f2b-111">El depurador debe llamar a este método en lugar de al método `GetThreadContext` de Win32, porque el subproceso puede estar realmente en un estado "secuestrado", en el que su contexto ha cambiado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="73f2b-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="73f2b-112">Este método solo se debe usar cuando un subproceso está en código nativo.</span><span class="sxs-lookup"><span data-stu-id="73f2b-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="73f2b-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) para subprocesos en código administrado.</span><span class="sxs-lookup"><span data-stu-id="73f2b-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="73f2b-114">Los datos devueltos son una estructura de contexto para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="73f2b-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="73f2b-115">Al igual que con el método de `GetThreadContext` de Win32, el llamador debe inicializar el parámetro `context` antes de llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="73f2b-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73f2b-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73f2b-116">Requirements</span></span>  
 <span data-ttu-id="73f2b-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73f2b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73f2b-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73f2b-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73f2b-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73f2b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73f2b-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73f2b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
