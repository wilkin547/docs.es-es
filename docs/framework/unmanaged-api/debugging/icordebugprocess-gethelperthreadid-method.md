---
title: ICorDebugProcess::GetHelperThreadID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
ms.openlocfilehash: fc4f4b56552c4db265d2ea123a84c7792ad53094
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213639"
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="b2257-102">ICorDebugProcess::GetHelperThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="b2257-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="b2257-103">Obtiene el identificador del subproceso del sistema operativo (SO) del subproceso auxiliar interno del depurador.</span><span class="sxs-lookup"><span data-stu-id="b2257-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2257-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2257-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2257-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2257-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="b2257-106">enuncia Puntero al identificador de subproceso del sistema operativo del subproceso auxiliar interno del depurador.</span><span class="sxs-lookup"><span data-stu-id="b2257-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2257-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b2257-107">Remarks</span></span>  
 <span data-ttu-id="b2257-108">Durante la depuración administrada y no administrada, es responsabilidad del depurador asegurarse de que el subproceso con el identificador especificado permanece en ejecución si llega a un punto de interrupción colocado por el depurador.</span><span class="sxs-lookup"><span data-stu-id="b2257-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="b2257-109">Un depurador también puede querer ocultar este subproceso al usuario.</span><span class="sxs-lookup"><span data-stu-id="b2257-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="b2257-110">Si aún no existe ningún subproceso auxiliar en el proceso, el `GetHelperThreadID` método devuelve cero en \* `pThreadID` .</span><span class="sxs-lookup"><span data-stu-id="b2257-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in \*`pThreadID`.</span></span>  
  
 <span data-ttu-id="b2257-111">No se puede almacenar en caché el identificador del subproceso auxiliar, ya que puede cambiar con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="b2257-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="b2257-112">Debe volver a consultar el identificador del subproceso en cada evento de detención.</span><span class="sxs-lookup"><span data-stu-id="b2257-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="b2257-113">El identificador de subproceso del subproceso auxiliar del depurador será correcto en cada evento [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) no administrado, lo que permite que un depurador determine el identificador de subproceso de su subproceso auxiliar y lo oculte del usuario.</span><span class="sxs-lookup"><span data-stu-id="b2257-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="b2257-114">Un subproceso que se identifica como un subproceso auxiliar durante un evento no administrado `ICorDebugManagedCallback::CreateThread` nunca ejecutará código de usuario administrado.</span><span class="sxs-lookup"><span data-stu-id="b2257-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2257-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2257-115">Requirements</span></span>  
 <span data-ttu-id="b2257-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2257-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2257-117">**Encabezado:** Cordebug. idl.</span><span class="sxs-lookup"><span data-stu-id="b2257-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="b2257-118">Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="b2257-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="b2257-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2257-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2257-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2257-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
