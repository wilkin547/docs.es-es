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
ms.openlocfilehash: 354df02b27e87550ba602fe102352455c227441b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859682"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="cac3d-102">ICorDebug::CanLaunchOrAttach (Método)</span><span class="sxs-lookup"><span data-stu-id="cac3d-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="cac3d-103">Devuelve un valor HRESULT que indica si el inicio de un nuevo proceso o la asociación al proceso existente especificado es posible en el contexto del equipo actual y de la configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cac3d-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cac3d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cac3d-104">Syntax</span></span>  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cac3d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cac3d-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="cac3d-106">de IDENTIFICADOR de un proceso existente.</span><span class="sxs-lookup"><span data-stu-id="cac3d-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="cac3d-107">de Pase `true` si tiene previsto iniciar con la depuración de Win32 habilitada o para asociarla con la depuración de Win32 habilitada; de lo contrario `false`, pase.</span><span class="sxs-lookup"><span data-stu-id="cac3d-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cac3d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cac3d-108">Return Value</span></span>  
 <span data-ttu-id="cac3d-109">S_OK si los servicios de depuración determinan que es posible iniciar un nuevo proceso o asociarse al proceso dado, dada la información sobre la configuración del equipo y el tiempo de ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="cac3d-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="cac3d-110">Los valores HRESULT posibles son:</span><span class="sxs-lookup"><span data-stu-id="cac3d-110">Possible HRESULT values are:</span></span>  
  
- <span data-ttu-id="cac3d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cac3d-111">S_OK</span></span>  
  
- <span data-ttu-id="cac3d-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="cac3d-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
- <span data-ttu-id="cac3d-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="cac3d-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
- <span data-ttu-id="cac3d-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="cac3d-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cac3d-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cac3d-115">Remarks</span></span>  
 <span data-ttu-id="cac3d-116">Este método es meramente informativo.</span><span class="sxs-lookup"><span data-stu-id="cac3d-116">This method is purely informational.</span></span> <span data-ttu-id="cac3d-117">La interfaz no impedirá que se inicie o se adjunte a un proceso, independientemente del valor devuelto por `CanLaunchOrAttach`.</span><span class="sxs-lookup"><span data-stu-id="cac3d-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="cac3d-118">Si planea iniciar con la depuración de Win32 habilitada o asociarla con la depuración de Win32 habilitada, pase `true` para `win32DebuggingEnabled`.</span><span class="sxs-lookup"><span data-stu-id="cac3d-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="cac3d-119">El HRESULT devuelto `CanLaunchOrAttach` por puede diferir si se usa esta opción.</span><span class="sxs-lookup"><span data-stu-id="cac3d-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cac3d-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cac3d-120">Requirements</span></span>  
 <span data-ttu-id="cac3d-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cac3d-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cac3d-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cac3d-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cac3d-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cac3d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cac3d-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cac3d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac3d-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cac3d-125">See also</span></span>

- [<span data-ttu-id="cac3d-126">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cac3d-126">ICorDebug Interface</span></span>](icordebug-interface.md)
