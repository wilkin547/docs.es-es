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
ms.openlocfilehash: 66d544bbc0511ea76565376c8f10294f1758026b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792569"
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="8cd53-102">ICorDebugProcess::SetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="8cd53-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="8cd53-103">Establece el contexto para el subproceso dado en este proceso.</span><span class="sxs-lookup"><span data-stu-id="8cd53-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cd53-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8cd53-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cd53-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8cd53-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="8cd53-106">de IDENTIFICADOR del subproceso para el que se va a establecer el contexto.</span><span class="sxs-lookup"><span data-stu-id="8cd53-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="8cd53-107">[in] Tamaño de la matriz `context`.</span><span class="sxs-lookup"><span data-stu-id="8cd53-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="8cd53-108">de Matriz de bytes que describen el contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8cd53-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="8cd53-109">El contexto especifica la arquitectura del procesador en el que se ejecuta el subproceso.</span><span class="sxs-lookup"><span data-stu-id="8cd53-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cd53-110">Notas</span><span class="sxs-lookup"><span data-stu-id="8cd53-110">Remarks</span></span>  
 <span data-ttu-id="8cd53-111">El depurador debe llamar a este método en lugar de a la función `SetThreadContext` de Win32, porque el subproceso puede estar realmente en un estado "secuestrado", en el que su contexto ha cambiado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="8cd53-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="8cd53-112">Este método solo se debe usar cuando un subproceso está en código nativo.</span><span class="sxs-lookup"><span data-stu-id="8cd53-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="8cd53-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) para subprocesos en código administrado.</span><span class="sxs-lookup"><span data-stu-id="8cd53-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="8cd53-114">Nunca debe modificar el contexto de un subproceso durante un evento de depuración fuera de banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="8cd53-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="8cd53-115">Los datos pasados deben ser una estructura de contexto para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="8cd53-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="8cd53-116">Este método puede dañar el tiempo de ejecución si se usa de forma incorrecta.</span><span class="sxs-lookup"><span data-stu-id="8cd53-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cd53-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="8cd53-117">Requirements</span></span>  
 <span data-ttu-id="8cd53-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cd53-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cd53-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8cd53-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cd53-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cd53-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cd53-121">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cd53-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
