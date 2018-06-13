---
title: ICorDebug::CanLaunchOrAttach (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f86cc83936dd8150ca6b3f28c9b6a624278e2b36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406297"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="2d1d2-102">ICorDebug::CanLaunchOrAttach (Método)</span><span class="sxs-lookup"><span data-stu-id="2d1d2-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="2d1d2-103">Devuelve un valor HRESULT que indica si iniciar un nuevo proceso o asociarse al proceso especificado existente es posible en el contexto de la configuración de máquina y en tiempo de ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="2d1d2-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d1d2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d1d2-104">Syntax</span></span>  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d1d2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d1d2-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="2d1d2-106">[in] El identificador de un proceso existente.</span><span class="sxs-lookup"><span data-stu-id="2d1d2-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="2d1d2-107">[in] Pasar `true` si va a iniciar con depuración de Win32 habilitada, o para asociar con la depuración de Win32 habilitada; en caso contrario, pase `false`.</span><span class="sxs-lookup"><span data-stu-id="2d1d2-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d1d2-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2d1d2-108">Return Value</span></span>  
 <span data-ttu-id="2d1d2-109">S_OK si determinan los servicios de depuración que inicie un nuevo proceso o asociarse al proceso determinado es posible que, dada la información sobre la configuración de máquina y en tiempo de ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="2d1d2-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="2d1d2-110">Valores HRESULT posibles son:</span><span class="sxs-lookup"><span data-stu-id="2d1d2-110">Possible HRESULT values are:</span></span>  
  
-   <span data-ttu-id="2d1d2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d1d2-111">S_OK</span></span>  
  
-   <span data-ttu-id="2d1d2-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="2d1d2-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
-   <span data-ttu-id="2d1d2-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="2d1d2-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
-   <span data-ttu-id="2d1d2-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="2d1d2-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d1d2-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d1d2-115">Remarks</span></span>  
 <span data-ttu-id="2d1d2-116">Este método es meramente informativo.</span><span class="sxs-lookup"><span data-stu-id="2d1d2-116">This method is purely informational.</span></span> <span data-ttu-id="2d1d2-117">La interfaz no detendrá de iniciar o asociar a un proceso, independientemente del valor devuelto por `CanLaunchOrAttach`.</span><span class="sxs-lookup"><span data-stu-id="2d1d2-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="2d1d2-118">Si tiene previsto iniciar con depuración de Win32 habilitada o conectar con la depuración de Win32 habilitada, pasar `true` para `win32DebuggingEnabled`.</span><span class="sxs-lookup"><span data-stu-id="2d1d2-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="2d1d2-119">El valor HRESULT devuelto por `CanLaunchOrAttach` pueden diferir si utiliza esta opción.</span><span class="sxs-lookup"><span data-stu-id="2d1d2-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d1d2-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d1d2-120">Requirements</span></span>  
 <span data-ttu-id="2d1d2-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d1d2-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d1d2-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d1d2-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d1d2-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d1d2-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d1d2-124">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d1d2-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d1d2-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d1d2-125">See Also</span></span>  
 [<span data-ttu-id="2d1d2-126">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d1d2-126">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
