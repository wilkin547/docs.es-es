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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd5e30d08e667dcd5a8be1f9502462f28290068e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987745"
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="8f220-102">ICorDebugProcess::GetHelperThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="8f220-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="8f220-103">Obtiene el identificador de subproceso del sistema operativo (SO) del subproceso auxiliar interno del depurador.</span><span class="sxs-lookup"><span data-stu-id="8f220-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f220-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f220-104">Syntax</span></span>  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f220-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f220-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="8f220-106">[out] Id. de subproceso auxiliar interno del depurador de subproceso de un puntero al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8f220-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f220-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8f220-107">Remarks</span></span>  
 <span data-ttu-id="8f220-108">Durante la depuración administrada y no administrados, es responsabilidad del depurador para asegurarse de que el subproceso con el identificador especificado sigue ejecutándose si se produce un punto de interrupción colocado por el depurador.</span><span class="sxs-lookup"><span data-stu-id="8f220-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="8f220-109">Un depurador que también desee ocultar este subproceso del usuario.</span><span class="sxs-lookup"><span data-stu-id="8f220-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="8f220-110">Si no hay ningún subproceso auxiliar existe en el proceso todavía, el `GetHelperThreadID` método devuelve cero en \*`pThreadID`.</span><span class="sxs-lookup"><span data-stu-id="8f220-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in \*`pThreadID`.</span></span>  
  
 <span data-ttu-id="8f220-111">No se almacena en caché el identificador de subproceso del subproceso de aplicación auxiliar, ya que puede cambiar con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="8f220-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="8f220-112">Debe volver a consultar el identificador de subproceso en cada evento de detención.</span><span class="sxs-lookup"><span data-stu-id="8f220-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="8f220-113">El identificador de subproceso del subproceso auxiliar del depurador será correcto en cada no administrado [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) eventos, lo que permite a un depurador determinar el identificador de subproceso de su subproceso auxiliar y ocultarla del usuario.</span><span class="sxs-lookup"><span data-stu-id="8f220-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="8f220-114">Un subproceso que se identifica como un subproceso auxiliar durante no administradas `ICorDebugManagedCallback::CreateThread` evento nunca ejecutará el código de usuario administrado.</span><span class="sxs-lookup"><span data-stu-id="8f220-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f220-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f220-115">Requirements</span></span>  
 <span data-ttu-id="8f220-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f220-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f220-117">**Encabezado**: CorDebug.idl.</span><span class="sxs-lookup"><span data-stu-id="8f220-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="8f220-118">CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f220-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="8f220-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f220-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f220-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f220-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
