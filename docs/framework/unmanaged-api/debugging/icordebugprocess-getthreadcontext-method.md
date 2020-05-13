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
ms.openlocfilehash: 2bdbf373144e2fb49074cfd035e7b0ffe3c8c291
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212898"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="86df5-102">ICorDebugProcess::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="86df5-102">ICorDebugProcess::GetThreadContext Method</span></span>
<span data-ttu-id="86df5-103">Obtiene el contexto para el subproceso dado en este proceso.</span><span class="sxs-lookup"><span data-stu-id="86df5-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86df5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86df5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86df5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86df5-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="86df5-106">de IDENTIFICADOR del subproceso para el que se va a recuperar el contexto.</span><span class="sxs-lookup"><span data-stu-id="86df5-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="86df5-107">[in] Tamaño de la matriz `context`.</span><span class="sxs-lookup"><span data-stu-id="86df5-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="86df5-108">[in, out] Matriz de bytes que describen el contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="86df5-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="86df5-109">El contexto especifica la arquitectura del procesador en el que se ejecuta el subproceso.</span><span class="sxs-lookup"><span data-stu-id="86df5-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86df5-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="86df5-110">Remarks</span></span>  
 <span data-ttu-id="86df5-111">El depurador debe llamar a este método en lugar de al `GetThreadContext` método Win32, ya que el subproceso puede estar realmente en un estado "secuestrado", en el que su contexto ha cambiado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="86df5-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="86df5-112">Este método solo se debe usar cuando un subproceso está en código nativo.</span><span class="sxs-lookup"><span data-stu-id="86df5-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="86df5-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) para subprocesos en código administrado.</span><span class="sxs-lookup"><span data-stu-id="86df5-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="86df5-114">Los datos devueltos son una estructura de contexto para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="86df5-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="86df5-115">Al igual que con el `GetThreadContext` método de Win32, el llamador debe inicializar el `context` parámetro antes de llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="86df5-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86df5-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86df5-116">Requirements</span></span>  
 <span data-ttu-id="86df5-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86df5-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86df5-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86df5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86df5-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86df5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86df5-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86df5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
