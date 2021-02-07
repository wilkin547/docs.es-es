---
description: 'Más información sobre: ICorDebugController:: Continue (método)'
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
ms.openlocfilehash: e5858a8c287e8dd5a493a85c9f427ad8acd9ecc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710808"
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="592f7-103">ICorDebugController::Continue (Método)</span><span class="sxs-lookup"><span data-stu-id="592f7-103">ICorDebugController::Continue Method</span></span>

<span data-ttu-id="592f7-104">Reanuda la ejecución de subprocesos administrados después de una llamada al [método STOP](icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="592f7-104">Resumes execution of managed threads after a call to [Stop Method](icordebugcontroller-stop-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="592f7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="592f7-105">Syntax</span></span>

```cpp
HRESULT Continue (
    [in] BOOL fIsOutOfBand
);
```

## <a name="parameters"></a><span data-ttu-id="592f7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="592f7-106">Parameters</span></span>

`fIsOutOfBand`  
<span data-ttu-id="592f7-107">de Se establece en `true` si se continúa desde un evento fuera de banda; de lo contrario, se establece en `false` .</span><span class="sxs-lookup"><span data-stu-id="592f7-107">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="592f7-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="592f7-108">Remarks</span></span>

<span data-ttu-id="592f7-109">`Continue` continúa el proceso después de una llamada al `ICorDebugController::Stop` método.</span><span class="sxs-lookup"><span data-stu-id="592f7-109">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>

<span data-ttu-id="592f7-110">Al realizar la depuración en modo mixto, no llame a `Continue` en el subproceso de eventos Win32 a menos que vaya a continuación de un evento fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="592f7-110">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>

<span data-ttu-id="592f7-111">Un *evento en banda* es un evento administrado o un evento no administrado normal durante el cual el depurador admite la interacción con el estado administrado del proceso.</span><span class="sxs-lookup"><span data-stu-id="592f7-111">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="592f7-112">En este caso, el depurador recibe la devolución de llamada [ICorDebugUnmanagedCallback (::D ebugevent](icordebugunmanagedcallback-debugevent-method.md) con su `fOutOfBand` parámetro establecido en `false` .</span><span class="sxs-lookup"><span data-stu-id="592f7-112">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>

<span data-ttu-id="592f7-113">Un *evento fuera de banda* es un evento no administrado durante el cual no es posible la interacción con el estado administrado del proceso mientras se detiene el proceso debido al evento.</span><span class="sxs-lookup"><span data-stu-id="592f7-113">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="592f7-114">En este caso, el depurador recibe la `ICorDebugUnmanagedCallback::DebugEvent` devolución de llamada con su `fOutOfBand` parámetro establecido en `true` .</span><span class="sxs-lookup"><span data-stu-id="592f7-114">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>

## <a name="requirements"></a><span data-ttu-id="592f7-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="592f7-115">Requirements</span></span>

<span data-ttu-id="592f7-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="592f7-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="592f7-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="592f7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="592f7-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="592f7-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="592f7-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="592f7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
