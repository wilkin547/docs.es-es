---
description: 'Más información acerca de: ICorDebugProcess:: GetThreadContext (método)'
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
ms.openlocfilehash: 4cb926183522548e924013580f207d1d0677a0d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746872"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="318e3-103">ICorDebugProcess::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="318e3-103">ICorDebugProcess::GetThreadContext Method</span></span>

<span data-ttu-id="318e3-104">Obtiene el contexto para el subproceso dado en este proceso.</span><span class="sxs-lookup"><span data-stu-id="318e3-104">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="318e3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="318e3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="318e3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="318e3-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="318e3-107">de IDENTIFICADOR del subproceso para el que se va a recuperar el contexto.</span><span class="sxs-lookup"><span data-stu-id="318e3-107">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="318e3-108">[in] Tamaño de la matriz `context`.</span><span class="sxs-lookup"><span data-stu-id="318e3-108">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="318e3-109">[in, out] Matriz de bytes que describen el contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="318e3-109">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="318e3-110">El contexto especifica la arquitectura del procesador en el que se ejecuta el subproceso.</span><span class="sxs-lookup"><span data-stu-id="318e3-110">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="318e3-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="318e3-111">Remarks</span></span>  

 <span data-ttu-id="318e3-112">El depurador debe llamar a este método en lugar de al `GetThreadContext` método Win32, ya que el subproceso puede estar realmente en un estado "secuestrado", en el que su contexto ha cambiado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="318e3-112">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="318e3-113">Este método solo se debe usar cuando un subproceso está en código nativo.</span><span class="sxs-lookup"><span data-stu-id="318e3-113">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="318e3-114">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) para subprocesos en código administrado.</span><span class="sxs-lookup"><span data-stu-id="318e3-114">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="318e3-115">Los datos devueltos son una estructura de contexto para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="318e3-115">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="318e3-116">Al igual que con el `GetThreadContext` método de Win32, el llamador debe inicializar el `context` parámetro antes de llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="318e3-116">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="318e3-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="318e3-117">Requirements</span></span>  

 <span data-ttu-id="318e3-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="318e3-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="318e3-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="318e3-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="318e3-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="318e3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="318e3-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="318e3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
