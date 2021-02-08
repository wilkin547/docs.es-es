---
description: 'Más información acerca de: ICorDebugProcess:: GetHelperThreadID ((método)'
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
ms.openlocfilehash: ee7bd2106a37c5c67df48a54ff9ab7fa49a03f80
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801025"
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="5b9e7-103">ICorDebugProcess::GetHelperThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="5b9e7-103">ICorDebugProcess::GetHelperThreadID Method</span></span>

<span data-ttu-id="5b9e7-104">Obtiene el identificador del subproceso del sistema operativo (SO) del subproceso auxiliar interno del depurador.</span><span class="sxs-lookup"><span data-stu-id="5b9e7-104">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b9e7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b9e7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b9e7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5b9e7-106">Parameters</span></span>  

 `pThreadID`  
 <span data-ttu-id="5b9e7-107">enuncia Puntero al identificador de subproceso del sistema operativo del subproceso auxiliar interno del depurador.</span><span class="sxs-lookup"><span data-stu-id="5b9e7-107">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b9e7-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5b9e7-108">Remarks</span></span>  

 <span data-ttu-id="5b9e7-109">Durante la depuración administrada y no administrada, es responsabilidad del depurador asegurarse de que el subproceso con el identificador especificado permanece en ejecución si llega a un punto de interrupción colocado por el depurador.</span><span class="sxs-lookup"><span data-stu-id="5b9e7-109">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="5b9e7-110">Un depurador también puede querer ocultar este subproceso al usuario.</span><span class="sxs-lookup"><span data-stu-id="5b9e7-110">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="5b9e7-111">Si aún no existe ningún subproceso auxiliar en el proceso, el `GetHelperThreadID` método devuelve cero en \* `pThreadID` .</span><span class="sxs-lookup"><span data-stu-id="5b9e7-111">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in \*`pThreadID`.</span></span>  
  
 <span data-ttu-id="5b9e7-112">No se puede almacenar en caché el identificador del subproceso auxiliar, ya que puede cambiar con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="5b9e7-112">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="5b9e7-113">Debe volver a consultar el identificador del subproceso en cada evento de detención.</span><span class="sxs-lookup"><span data-stu-id="5b9e7-113">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="5b9e7-114">El identificador de subproceso del subproceso auxiliar del depurador será correcto en cada evento [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) no administrado, lo que permite que un depurador determine el identificador de subproceso de su subproceso auxiliar y lo oculte del usuario.</span><span class="sxs-lookup"><span data-stu-id="5b9e7-114">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="5b9e7-115">Un subproceso que se identifica como un subproceso auxiliar durante un evento no administrado `ICorDebugManagedCallback::CreateThread` nunca ejecutará código de usuario administrado.</span><span class="sxs-lookup"><span data-stu-id="5b9e7-115">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b9e7-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b9e7-116">Requirements</span></span>  

 <span data-ttu-id="5b9e7-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b9e7-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b9e7-118">**Encabezado:** Cordebug. idl.</span><span class="sxs-lookup"><span data-stu-id="5b9e7-118">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="5b9e7-119">Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="5b9e7-119">CorDebug.h</span></span>  
  
 <span data-ttu-id="5b9e7-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b9e7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b9e7-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b9e7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
