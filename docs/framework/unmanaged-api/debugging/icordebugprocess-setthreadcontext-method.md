---
description: 'Más información acerca de: ICorDebugProcess:: SetThreadContext (método)'
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
ms.openlocfilehash: 3576c3bf3159e3960e7d2d4601ac2fb67d7218f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753983"
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="8cf15-103">ICorDebugProcess::SetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="8cf15-103">ICorDebugProcess::SetThreadContext Method</span></span>

<span data-ttu-id="8cf15-104">Establece el contexto para el subproceso dado en este proceso.</span><span class="sxs-lookup"><span data-stu-id="8cf15-104">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cf15-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8cf15-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cf15-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8cf15-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="8cf15-107">de IDENTIFICADOR del subproceso para el que se va a establecer el contexto.</span><span class="sxs-lookup"><span data-stu-id="8cf15-107">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="8cf15-108">[in] Tamaño de la matriz `context`.</span><span class="sxs-lookup"><span data-stu-id="8cf15-108">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="8cf15-109">de Matriz de bytes que describen el contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8cf15-109">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="8cf15-110">El contexto especifica la arquitectura del procesador en el que se ejecuta el subproceso.</span><span class="sxs-lookup"><span data-stu-id="8cf15-110">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cf15-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8cf15-111">Remarks</span></span>  

 <span data-ttu-id="8cf15-112">El depurador debe llamar a este método en lugar de a la función de Win32 `SetThreadContext` , ya que el subproceso puede estar realmente en un estado "secuestrado", en el que su contexto ha cambiado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="8cf15-112">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="8cf15-113">Este método solo se debe usar cuando un subproceso está en código nativo.</span><span class="sxs-lookup"><span data-stu-id="8cf15-113">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="8cf15-114">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) para subprocesos en código administrado.</span><span class="sxs-lookup"><span data-stu-id="8cf15-114">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="8cf15-115">Nunca debe modificar el contexto de un subproceso durante un evento de depuración fuera de banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="8cf15-115">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="8cf15-116">Los datos pasados deben ser una estructura de contexto para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="8cf15-116">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="8cf15-117">Este método puede dañar el tiempo de ejecución si se usa de forma incorrecta.</span><span class="sxs-lookup"><span data-stu-id="8cf15-117">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cf15-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8cf15-118">Requirements</span></span>  

 <span data-ttu-id="8cf15-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cf15-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cf15-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8cf15-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cf15-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cf15-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cf15-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cf15-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
