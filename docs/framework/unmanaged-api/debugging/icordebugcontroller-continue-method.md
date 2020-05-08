---
title: ICorDebugController::Continue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
ms.openlocfilehash: 0fd7dfc1a48e21abbc80692c110bee55beb68e6b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892864"
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="25948-102">ICorDebugController::Continue (Método)</span><span class="sxs-lookup"><span data-stu-id="25948-102">ICorDebugController::Continue Method</span></span>

<span data-ttu-id="25948-103">Reanuda la ejecución de subprocesos administrados después de una llamada al [método STOP](icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="25948-103">Resumes execution of managed threads after a call to [Stop Method](icordebugcontroller-stop-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="25948-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25948-104">Syntax</span></span>

```cpp
HRESULT Continue (
    [in] BOOL fIsOutOfBand
);
```

## <a name="parameters"></a><span data-ttu-id="25948-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25948-105">Parameters</span></span>

`fIsOutOfBand`  
<span data-ttu-id="25948-106">de Se establece `true` en si se continúa desde un evento fuera de banda; en caso contrario, `false`establezca en.</span><span class="sxs-lookup"><span data-stu-id="25948-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="25948-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="25948-107">Remarks</span></span>

<span data-ttu-id="25948-108">`Continue`continúa el proceso después de una llamada al `ICorDebugController::Stop` método.</span><span class="sxs-lookup"><span data-stu-id="25948-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>

<span data-ttu-id="25948-109">Al realizar la depuración en modo mixto, no `Continue` llame a en el subproceso de eventos Win32 a menos que vaya a continuación de un evento fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="25948-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>

<span data-ttu-id="25948-110">Un *evento en banda* es un evento administrado o un evento no administrado normal durante el cual el depurador admite la interacción con el estado administrado del proceso.</span><span class="sxs-lookup"><span data-stu-id="25948-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="25948-111">En este caso, el depurador recibe la devolución de llamada [ICorDebugUnmanagedCallback (::D ebugevent](icordebugunmanagedcallback-debugevent-method.md) con `fOutOfBand` su `false`parámetro establecido en.</span><span class="sxs-lookup"><span data-stu-id="25948-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>

<span data-ttu-id="25948-112">Un *evento fuera de banda* es un evento no administrado durante el cual no es posible la interacción con el estado administrado del proceso mientras se detiene el proceso debido al evento.</span><span class="sxs-lookup"><span data-stu-id="25948-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="25948-113">En este caso, el depurador recibe `ICorDebugUnmanagedCallback::DebugEvent` la devolución de `fOutOfBand` llamada con su `true`parámetro establecido en.</span><span class="sxs-lookup"><span data-stu-id="25948-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>

## <a name="requirements"></a><span data-ttu-id="25948-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25948-114">Requirements</span></span>

<span data-ttu-id="25948-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25948-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="25948-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25948-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="25948-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25948-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="25948-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25948-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
