---
title: "ICorDebugProcess::IsOSSuspended (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.IsOSSuspended
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 97c394e3084007227cf157c62a12df3f5cfac8e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="81570-102">ICorDebugProcess::IsOSSuspended (Método)</span><span class="sxs-lookup"><span data-stu-id="81570-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="81570-103">Obtiene un valor que indica si el subproceso especificado se ha suspendido porque el depurador detener este proceso.</span><span class="sxs-lookup"><span data-stu-id="81570-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81570-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81570-104">Syntax</span></span>  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81570-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81570-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="81570-106">[in] El identificador del subproceso en cuestión.</span><span class="sxs-lookup"><span data-stu-id="81570-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="81570-107">[out] Un puntero a un valor booleano que es `true` si el subproceso especificado se ha suspendido; de lo contrario *`pbSuspended` es `false`.</span><span class="sxs-lookup"><span data-stu-id="81570-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise *`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81570-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="81570-108">Remarks</span></span>  
 <span data-ttu-id="81570-109">Cuando el subproceso especificado se ha suspendido porque el depurador detener este proceso, el recuento de suspensiones de Win32 del subproceso especificado se incrementa en uno.</span><span class="sxs-lookup"><span data-stu-id="81570-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="81570-110">La interfaz de usuario (UI) del depurador puede tener en cuenta esta información si muestra el sistema operativo (SO) suspende el recuento del subproceso para el usuario.</span><span class="sxs-lookup"><span data-stu-id="81570-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="81570-111">El `IsOSSuspended` método tiene sentido sólo en el contexto de depuración no administrada.</span><span class="sxs-lookup"><span data-stu-id="81570-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="81570-112">Durante la depuración administrada, los subprocesos se forma cooperativa suspendido en lugar de suspendido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="81570-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81570-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81570-113">Requirements</span></span>  
 <span data-ttu-id="81570-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81570-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81570-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81570-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81570-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81570-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81570-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81570-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
