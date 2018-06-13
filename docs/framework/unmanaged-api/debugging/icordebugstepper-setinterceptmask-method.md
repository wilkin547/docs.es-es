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
ms.openlocfilehash: 7654a91180dd0b4148cfb85b35bf1ce730764f28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422690"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="9b698-102">ICorDebugStepper::SetInterceptMask (Método)</span><span class="sxs-lookup"><span data-stu-id="9b698-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="9b698-103">Establece un valor que especifica los tipos de código que se recorren paso a paso.</span><span class="sxs-lookup"><span data-stu-id="9b698-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b698-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b698-104">Syntax</span></span>  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b698-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9b698-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="9b698-106">[in] Una combinación de valores de la enumeración CorDebugIntercept que especifica los tipos de código.</span><span class="sxs-lookup"><span data-stu-id="9b698-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b698-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9b698-107">Remarks</span></span>  
 <span data-ttu-id="9b698-108">Si se establece el bit de un interceptor, el paso a paso desencadene se completará cuando se encuentra el tipo dado de código de intercepción.</span><span class="sxs-lookup"><span data-stu-id="9b698-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="9b698-109">Si el bit está desactivado, se omitirá el código de intercepción.</span><span class="sxs-lookup"><span data-stu-id="9b698-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="9b698-110">El `SetInterceptMask` el método podría tener interacciones imprevistas con [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (desde el punto de vista del usuario).</span><span class="sxs-lookup"><span data-stu-id="9b698-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="9b698-111">Por ejemplo, si solo visible (es decir, no interna) parte del código de inicialización de clase carece de información de asignación y STOP_NO_MAPPING_INFO no está establecido (vea la [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) método y la CorDebugUnmappedStop (enumeración)), el paso a paso desencadene recorre paso a paso sobre la inicialización de la clase.</span><span class="sxs-lookup"><span data-stu-id="9b698-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="9b698-112">De forma predeterminada, solo el valor INTERCEPT_NONE de la `CorDebugIntercept` se usará la enumeración.</span><span class="sxs-lookup"><span data-stu-id="9b698-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b698-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b698-113">Requirements</span></span>  
 <span data-ttu-id="9b698-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b698-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b698-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b698-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b698-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b698-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b698-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b698-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
