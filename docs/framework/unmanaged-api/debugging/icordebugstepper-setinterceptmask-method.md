---
title: ICorDebugStepper::SetInterceptMask (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
ms.openlocfilehash: aaba751a58e5b23b98b1d0629ea3cc9e1e7a83a9
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379007"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="b37e0-102">ICorDebugStepper::SetInterceptMask (Método)</span><span class="sxs-lookup"><span data-stu-id="b37e0-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="b37e0-103">Establece un valor que especifica los tipos de código a los que se va a recorrer.</span><span class="sxs-lookup"><span data-stu-id="b37e0-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b37e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b37e0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b37e0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b37e0-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="b37e0-106">de Combinación de valores de la enumeración Cordebugintercept (que especifica los tipos de código.</span><span class="sxs-lookup"><span data-stu-id="b37e0-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b37e0-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b37e0-107">Remarks</span></span>  
 <span data-ttu-id="b37e0-108">Si se establece el bit de un interceptor, el stepper se completará cuando se encuentre el tipo de código de interceptación especificado.</span><span class="sxs-lookup"><span data-stu-id="b37e0-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="b37e0-109">Si el bit está desactivado, se omitirá el código de intercepción.</span><span class="sxs-lookup"><span data-stu-id="b37e0-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="b37e0-110">El `SetInterceptMask` método puede tener interacciones imprevistas con [ICorDebugStepper:: setunmappedstopmask (](icordebugstepper-setunmappedstopmask-method.md) (desde el punto de vista del usuario).</span><span class="sxs-lookup"><span data-stu-id="b37e0-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="b37e0-111">Por ejemplo, si la única parte visible (es decir, no interna) del código de inicialización de clase no tiene información de asignación y STOP_NO_MAPPING_INFO no está establecido (vea el método [ICorDebugStepper:: setunmappedstopmask (](icordebugstepper-setunmappedstopmask-method.md) y la enumeración cordebugunmappedstop (), el stepper desplazará sobre la inicialización de la clase.</span><span class="sxs-lookup"><span data-stu-id="b37e0-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="b37e0-112">De forma predeterminada, solo se utilizará el valor INTERCEPT_NONE de la `CorDebugIntercept` enumeración.</span><span class="sxs-lookup"><span data-stu-id="b37e0-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b37e0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b37e0-113">Requirements</span></span>  
 <span data-ttu-id="b37e0-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b37e0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b37e0-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b37e0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b37e0-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b37e0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b37e0-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b37e0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
