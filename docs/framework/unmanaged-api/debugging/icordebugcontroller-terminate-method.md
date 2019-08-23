---
title: ICorDebugController::Terminate (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee1c30809567097e67b6b1e40f5534429d748abd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964367"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="b3b6d-102">ICorDebugController::Terminate (Método)</span><span class="sxs-lookup"><span data-stu-id="b3b6d-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="b3b6d-103">Finaliza el proceso con el código de salida especificado.</span><span class="sxs-lookup"><span data-stu-id="b3b6d-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3b6d-104">Este método es un contenedor para la función `TerminateProcess` de Win32.</span><span class="sxs-lookup"><span data-stu-id="b3b6d-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="b3b6d-105">Por lo `Terminate` tanto, utiliza el código de salida del mismo modo que `TerminateProcess` la función de Win32 lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="b3b6d-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3b6d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3b6d-106">Syntax</span></span>  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3b6d-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b3b6d-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="b3b6d-108">de Un valor numérico que es el código de salida.</span><span class="sxs-lookup"><span data-stu-id="b3b6d-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="b3b6d-109">Los valores numéricos válidos se definen en Winbase. h.</span><span class="sxs-lookup"><span data-stu-id="b3b6d-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3b6d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b3b6d-110">Remarks</span></span>  
 <span data-ttu-id="b3b6d-111">Si el proceso se detiene cuando `Terminate` se llama a, el proceso debe continuar usando el método [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) para que el depurador reciba la confirmación de la finalización a través de [ICorDebugManagedCallback:: ](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)La devolución de llamada ExitProcess o [ICorDebugManagedCallback:: exitappdomain (](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b3b6d-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3b6d-112">Este método no está implementado por un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b3b6d-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="b3b6d-113">Es decir, no se implementa en el <xref:System.AppDomain> nivel.</span><span class="sxs-lookup"><span data-stu-id="b3b6d-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3b6d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3b6d-114">Requirements</span></span>  
 <span data-ttu-id="b3b6d-115">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3b6d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3b6d-116">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="b3b6d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3b6d-117">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3b6d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3b6d-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3b6d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3b6d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3b6d-119">See also</span></span>
