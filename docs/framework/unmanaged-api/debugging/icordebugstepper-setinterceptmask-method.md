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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37b644227a6085352bed682f0ddd7c3455b54895
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760701"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="0b2d0-102">ICorDebugStepper::SetInterceptMask (Método)</span><span class="sxs-lookup"><span data-stu-id="0b2d0-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="0b2d0-103">Establece un valor que especifica los tipos de código que se ejecutar paso a paso.</span><span class="sxs-lookup"><span data-stu-id="0b2d0-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b2d0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b2d0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b2d0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0b2d0-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="0b2d0-106">[in] Una combinación de valores de la enumeración CorDebugIntercept que especifica los tipos de código.</span><span class="sxs-lookup"><span data-stu-id="0b2d0-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b2d0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0b2d0-107">Remarks</span></span>  
 <span data-ttu-id="0b2d0-108">Si se establece el bit de un interceptor, el motor paso a paso se completará cuando se encuentra el tipo especificado de interceptar el código.</span><span class="sxs-lookup"><span data-stu-id="0b2d0-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="0b2d0-109">Si el bit está desactivado, se omitirá el código de intercepción.</span><span class="sxs-lookup"><span data-stu-id="0b2d0-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="0b2d0-110">El `SetInterceptMask` método puede tener interacciones imprevistas con [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (desde el punto de vista del usuario).</span><span class="sxs-lookup"><span data-stu-id="0b2d0-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="0b2d0-111">Por ejemplo, si solo está visible (es decir, no interna) parte del código de inicialización de clase carece de información de asignación y STOP_NO_MAPPING_INFO no está establecido (consulte la [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) método y el CorDebugUnmappedStop (enumeración)), el motor paso a paso le guiará a través de la inicialización de clase.</span><span class="sxs-lookup"><span data-stu-id="0b2d0-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="0b2d0-112">De forma predeterminada, solo el valor INTERCEPT_NONE de la `CorDebugIntercept` se usará la enumeración.</span><span class="sxs-lookup"><span data-stu-id="0b2d0-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b2d0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b2d0-113">Requirements</span></span>  
 <span data-ttu-id="0b2d0-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b2d0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b2d0-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b2d0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b2d0-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b2d0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b2d0-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b2d0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
