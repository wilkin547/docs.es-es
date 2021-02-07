---
description: 'Más información acerca de: ICorDebugController:: Terminate (método)'
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
ms.openlocfilehash: 15cc832205ebfe86e521d4a45124808e0f3fe128
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710717"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="f84b1-103">ICorDebugController::Terminate (Método)</span><span class="sxs-lookup"><span data-stu-id="f84b1-103">ICorDebugController::Terminate Method</span></span>

<span data-ttu-id="f84b1-104">Finaliza el proceso con el código de salida especificado.</span><span class="sxs-lookup"><span data-stu-id="f84b1-104">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f84b1-105">Este método es un contenedor para la función de Win32 `TerminateProcess` .</span><span class="sxs-lookup"><span data-stu-id="f84b1-105">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="f84b1-106">Por lo tanto, `Terminate` utiliza el código de salida del mismo modo que la función de Win32 `TerminateProcess` lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="f84b1-106">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f84b1-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f84b1-107">Syntax</span></span>  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f84b1-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f84b1-108">Parameters</span></span>  

 `exitCode`  
 <span data-ttu-id="f84b1-109">de Un valor numérico que es el código de salida.</span><span class="sxs-lookup"><span data-stu-id="f84b1-109">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="f84b1-110">Los valores numéricos válidos se definen en Winbase. h.</span><span class="sxs-lookup"><span data-stu-id="f84b1-110">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f84b1-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f84b1-111">Remarks</span></span>  

 <span data-ttu-id="f84b1-112">Si el proceso se detiene cuando `Terminate` se llama a, el proceso debe continuar usando el método [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) para que el depurador reciba la confirmación de la finalización a través de la devolución de llamada [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) o [ICorDebugManagedCallback:: exitappdomain (](icordebugmanagedcallback-exitappdomain-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f84b1-112">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f84b1-113">Este método no está implementado por un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f84b1-113">This method is not implemented by an application domain.</span></span> <span data-ttu-id="f84b1-114">Es decir, no se implementa en el <xref:System.AppDomain> nivel.</span><span class="sxs-lookup"><span data-stu-id="f84b1-114">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f84b1-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f84b1-115">Requirements</span></span>  

 <span data-ttu-id="f84b1-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f84b1-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f84b1-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f84b1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f84b1-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f84b1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f84b1-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f84b1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f84b1-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f84b1-120">See also</span></span>
