---
description: 'Más información acerca de: ICorDebug:: CanLaunchOrAttach ((método)'
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
ms.openlocfilehash: cb813c4bae968941de731d9d5b74d8f804b3c8ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723249"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="0f8d1-103">ICorDebug::CanLaunchOrAttach (Método)</span><span class="sxs-lookup"><span data-stu-id="0f8d1-103">ICorDebug::CanLaunchOrAttach Method</span></span>

<span data-ttu-id="0f8d1-104">Devuelve un valor HRESULT que indica si el inicio de un nuevo proceso o la asociación al proceso existente especificado es posible en el contexto del equipo actual y de la configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0f8d1-104">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f8d1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f8d1-105">Syntax</span></span>  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f8d1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f8d1-106">Parameters</span></span>  

 `dwProcessId`  
 <span data-ttu-id="0f8d1-107">de IDENTIFICADOR de un proceso existente.</span><span class="sxs-lookup"><span data-stu-id="0f8d1-107">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="0f8d1-108">de Pase `true` si tiene previsto iniciar con la depuración de Win32 habilitada o para asociarla con la depuración de Win32 habilitada; de lo contrario, pase `false` .</span><span class="sxs-lookup"><span data-stu-id="0f8d1-108">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f8d1-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0f8d1-109">Return Value</span></span>  

 <span data-ttu-id="0f8d1-110">S_OK si los servicios de depuración determinan que es posible iniciar un nuevo proceso o asociarse al proceso dado, dada la información sobre la configuración del equipo y el tiempo de ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="0f8d1-110">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="0f8d1-111">Los valores HRESULT posibles son:</span><span class="sxs-lookup"><span data-stu-id="0f8d1-111">Possible HRESULT values are:</span></span>  
  
- <span data-ttu-id="0f8d1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f8d1-112">S_OK</span></span>  
  
- <span data-ttu-id="0f8d1-113">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="0f8d1-113">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
- <span data-ttu-id="0f8d1-114">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="0f8d1-114">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
- <span data-ttu-id="0f8d1-115">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="0f8d1-115">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f8d1-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0f8d1-116">Remarks</span></span>  

 <span data-ttu-id="0f8d1-117">Este método es meramente informativo.</span><span class="sxs-lookup"><span data-stu-id="0f8d1-117">This method is purely informational.</span></span> <span data-ttu-id="0f8d1-118">La interfaz no impedirá que se inicie o se adjunte a un proceso, independientemente del valor devuelto por `CanLaunchOrAttach` .</span><span class="sxs-lookup"><span data-stu-id="0f8d1-118">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="0f8d1-119">Si planea iniciar con la depuración de Win32 habilitada o asociarla con la depuración de Win32 habilitada, pase `true` para `win32DebuggingEnabled` .</span><span class="sxs-lookup"><span data-stu-id="0f8d1-119">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="0f8d1-120">El HRESULT devuelto por `CanLaunchOrAttach` puede diferir si se usa esta opción.</span><span class="sxs-lookup"><span data-stu-id="0f8d1-120">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f8d1-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f8d1-121">Requirements</span></span>  

 <span data-ttu-id="0f8d1-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f8d1-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f8d1-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f8d1-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f8d1-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f8d1-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f8d1-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f8d1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f8d1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f8d1-126">See also</span></span>

- [<span data-ttu-id="0f8d1-127">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f8d1-127">ICorDebug Interface</span></span>](icordebug-interface.md)
