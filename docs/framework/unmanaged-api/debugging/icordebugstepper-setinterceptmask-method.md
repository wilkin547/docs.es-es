---
description: 'Más información acerca de: ICorDebugStepper:: Setinterceptmask ((método)'
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
ms.openlocfilehash: 33a42b154d063a29022034fd8061599a5e0e5503
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803553"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="9a839-103">ICorDebugStepper::SetInterceptMask (Método)</span><span class="sxs-lookup"><span data-stu-id="9a839-103">ICorDebugStepper::SetInterceptMask Method</span></span>

<span data-ttu-id="9a839-104">Establece un valor que especifica los tipos de código a los que se va a recorrer.</span><span class="sxs-lookup"><span data-stu-id="9a839-104">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a839-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a839-105">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a839-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a839-106">Parameters</span></span>  

 `mask`  
 <span data-ttu-id="9a839-107">de Combinación de valores de la enumeración Cordebugintercept (que especifica los tipos de código.</span><span class="sxs-lookup"><span data-stu-id="9a839-107">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a839-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9a839-108">Remarks</span></span>  

 <span data-ttu-id="9a839-109">Si se establece el bit de un interceptor, el stepper se completará cuando se encuentre el tipo de código de interceptación especificado.</span><span class="sxs-lookup"><span data-stu-id="9a839-109">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="9a839-110">Si el bit está desactivado, se omitirá el código de intercepción.</span><span class="sxs-lookup"><span data-stu-id="9a839-110">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="9a839-111">El `SetInterceptMask` método puede tener interacciones imprevistas con [ICorDebugStepper:: setunmappedstopmask (](icordebugstepper-setunmappedstopmask-method.md) (desde el punto de vista del usuario).</span><span class="sxs-lookup"><span data-stu-id="9a839-111">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="9a839-112">Por ejemplo, si la única parte visible (es decir, no interna) del código de inicialización de clase no tiene información de asignación y STOP_NO_MAPPING_INFO no está establecido (vea el método [ICorDebugStepper:: setunmappedstopmask (](icordebugstepper-setunmappedstopmask-method.md) y la enumeración cordebugunmappedstop (), el stepper desplazará sobre la inicialización de la clase.</span><span class="sxs-lookup"><span data-stu-id="9a839-112">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="9a839-113">De forma predeterminada, solo se utilizará el valor INTERCEPT_NONE de la `CorDebugIntercept` enumeración.</span><span class="sxs-lookup"><span data-stu-id="9a839-113">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a839-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a839-114">Requirements</span></span>  

 <span data-ttu-id="9a839-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a839-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a839-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a839-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a839-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a839-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a839-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a839-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
