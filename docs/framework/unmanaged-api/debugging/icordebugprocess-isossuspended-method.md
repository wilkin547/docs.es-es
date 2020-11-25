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
ms.openlocfilehash: fffa61d8e406162251b0934a9846e5a813422798
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724590"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="38255-102">ICorDebugProcess::IsOSSuspended (Método)</span><span class="sxs-lookup"><span data-stu-id="38255-102">ICorDebugProcess::IsOSSuspended Method</span></span>

<span data-ttu-id="38255-103">Obtiene un valor que indica si el subproceso especificado se ha suspendido como resultado de que el depurador detenga este proceso.</span><span class="sxs-lookup"><span data-stu-id="38255-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38255-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38255-104">Syntax</span></span>  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38255-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="38255-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="38255-106">de IDENTIFICADOR del subproceso en cuestión.</span><span class="sxs-lookup"><span data-stu-id="38255-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="38255-107">enuncia Un puntero a un valor booleano que es `true` si se ha suspendido el subproceso especificado; de lo contrario, \* `pbSuspended` es `false` .</span><span class="sxs-lookup"><span data-stu-id="38255-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38255-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38255-108">Remarks</span></span>  

 <span data-ttu-id="38255-109">Cuando el subproceso especificado se ha suspendido como resultado de que el depurador detenga este proceso, el recuento de suspensión de Win32 del subproceso especificado se incrementa en uno.</span><span class="sxs-lookup"><span data-stu-id="38255-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="38255-110">Es posible que la interfaz de usuario (UI) del depurador desee tener en cuenta esta información si muestra el recuento de suspensiones del sistema operativo (SO) del subproceso al usuario.</span><span class="sxs-lookup"><span data-stu-id="38255-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="38255-111">El `IsOSSuspended` método tiene sentido solo en el contexto de la depuración no administrada.</span><span class="sxs-lookup"><span data-stu-id="38255-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="38255-112">Durante la depuración administrada, los subprocesos se suspenden de forma cooperativa en lugar de suspender el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="38255-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38255-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38255-113">Requirements</span></span>  

 <span data-ttu-id="38255-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38255-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38255-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38255-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38255-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38255-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38255-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38255-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
