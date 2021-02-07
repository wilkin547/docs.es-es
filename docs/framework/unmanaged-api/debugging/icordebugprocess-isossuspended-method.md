---
description: 'Más información acerca de: ICorDebugProcess:: Isossuspended ((método)'
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
ms.openlocfilehash: aa5e438418330d9fee51fcdb56a617421df06904
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746777"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="c0a68-103">ICorDebugProcess::IsOSSuspended (Método)</span><span class="sxs-lookup"><span data-stu-id="c0a68-103">ICorDebugProcess::IsOSSuspended Method</span></span>

<span data-ttu-id="c0a68-104">Obtiene un valor que indica si el subproceso especificado se ha suspendido como resultado de que el depurador detenga este proceso.</span><span class="sxs-lookup"><span data-stu-id="c0a68-104">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0a68-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0a68-105">Syntax</span></span>  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0a68-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c0a68-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="c0a68-107">de IDENTIFICADOR del subproceso en cuestión.</span><span class="sxs-lookup"><span data-stu-id="c0a68-107">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="c0a68-108">enuncia Un puntero a un valor booleano que es `true` si se ha suspendido el subproceso especificado; de lo contrario, \* `pbSuspended` es `false` .</span><span class="sxs-lookup"><span data-stu-id="c0a68-108">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0a68-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c0a68-109">Remarks</span></span>  

 <span data-ttu-id="c0a68-110">Cuando el subproceso especificado se ha suspendido como resultado de que el depurador detenga este proceso, el recuento de suspensión de Win32 del subproceso especificado se incrementa en uno.</span><span class="sxs-lookup"><span data-stu-id="c0a68-110">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="c0a68-111">Es posible que la interfaz de usuario (UI) del depurador desee tener en cuenta esta información si muestra el recuento de suspensiones del sistema operativo (SO) del subproceso al usuario.</span><span class="sxs-lookup"><span data-stu-id="c0a68-111">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="c0a68-112">El `IsOSSuspended` método tiene sentido solo en el contexto de la depuración no administrada.</span><span class="sxs-lookup"><span data-stu-id="c0a68-112">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="c0a68-113">Durante la depuración administrada, los subprocesos se suspenden de forma cooperativa en lugar de suspender el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c0a68-113">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0a68-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0a68-114">Requirements</span></span>  

 <span data-ttu-id="c0a68-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0a68-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0a68-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0a68-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0a68-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0a68-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0a68-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0a68-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
