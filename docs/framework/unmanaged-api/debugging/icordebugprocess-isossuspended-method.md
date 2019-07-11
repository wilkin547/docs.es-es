---
title: ICorDebugProcess::IsOSSuspended (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 275f62c8211f71f067d310dd4b3af2ddb11e93d7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755458"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="e9bd1-102">ICorDebugProcess::IsOSSuspended (Método)</span><span class="sxs-lookup"><span data-stu-id="e9bd1-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="e9bd1-103">Obtiene un valor que indica si el subproceso especificado se ha suspendido porque el depurador detener este proceso.</span><span class="sxs-lookup"><span data-stu-id="e9bd1-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9bd1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9bd1-104">Syntax</span></span>  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9bd1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9bd1-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="e9bd1-106">[in] El identificador del subproceso en cuestión.</span><span class="sxs-lookup"><span data-stu-id="e9bd1-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="e9bd1-107">[out] Un puntero a un valor booleano que es `true` si el subproceso especificado se ha suspendido; de lo contrario \*`pbSuspended` es `false`.</span><span class="sxs-lookup"><span data-stu-id="e9bd1-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9bd1-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9bd1-108">Remarks</span></span>  
 <span data-ttu-id="e9bd1-109">Cuando el subproceso especificado se ha suspendido porque el depurador detener este proceso, el recuento de suspensiones de Win32 del subproceso especificado se incrementa en uno.</span><span class="sxs-lookup"><span data-stu-id="e9bd1-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="e9bd1-110">La interfaz de usuario (UI) de depurador que desee tener en cuenta esta información si muestra el sistema operativo (SO) suspende el recuento del subproceso para el usuario.</span><span class="sxs-lookup"><span data-stu-id="e9bd1-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="e9bd1-111">El `IsOSSuspended` método tiene sentido sólo en el contexto de depuración no administrada.</span><span class="sxs-lookup"><span data-stu-id="e9bd1-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="e9bd1-112">Durante la depuración administrada, los subprocesos son forma cooperativa suspendida en lugar del sistema operativo suspendido.</span><span class="sxs-lookup"><span data-stu-id="e9bd1-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9bd1-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9bd1-113">Requirements</span></span>  
 <span data-ttu-id="e9bd1-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9bd1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9bd1-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9bd1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9bd1-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9bd1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9bd1-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9bd1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
