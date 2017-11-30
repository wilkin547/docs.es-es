---
title: "ICorDebugStepper::SetInterceptMask (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.SetInterceptMask
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a99b504c0ce58ca6b89153667598cd4c2c682d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="1e43e-102">ICorDebugStepper::SetInterceptMask (Método)</span><span class="sxs-lookup"><span data-stu-id="1e43e-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="1e43e-103">Establece un valor que especifica los tipos de código que se recorren paso a paso.</span><span class="sxs-lookup"><span data-stu-id="1e43e-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e43e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e43e-104">Syntax</span></span>  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1e43e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1e43e-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="1e43e-106">[in] Una combinación de valores de la enumeración CorDebugIntercept que especifica los tipos de código.</span><span class="sxs-lookup"><span data-stu-id="1e43e-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e43e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1e43e-107">Remarks</span></span>  
 <span data-ttu-id="1e43e-108">Si se establece el bit de un interceptor, el paso a paso desencadene se completará cuando se encuentra el tipo dado de código de intercepción.</span><span class="sxs-lookup"><span data-stu-id="1e43e-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="1e43e-109">Si el bit está desactivado, se omitirá el código de intercepción.</span><span class="sxs-lookup"><span data-stu-id="1e43e-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="1e43e-110">El `SetInterceptMask` el método podría tener interacciones imprevistas con [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (desde el punto de vista del usuario).</span><span class="sxs-lookup"><span data-stu-id="1e43e-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="1e43e-111">Por ejemplo, si solo visible (es decir, no interna) parte del código de inicialización de clase carece de información de asignación y STOP_NO_MAPPING_INFO no está establecido (vea la [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) método y la CorDebugUnmappedStop (enumeración)), el paso a paso desencadene recorre paso a paso sobre la inicialización de la clase.</span><span class="sxs-lookup"><span data-stu-id="1e43e-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="1e43e-112">De forma predeterminada, solo el valor INTERCEPT_NONE de la `CorDebugIntercept` se usará la enumeración.</span><span class="sxs-lookup"><span data-stu-id="1e43e-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e43e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e43e-113">Requirements</span></span>  
 <span data-ttu-id="1e43e-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e43e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e43e-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e43e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e43e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e43e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e43e-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e43e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
