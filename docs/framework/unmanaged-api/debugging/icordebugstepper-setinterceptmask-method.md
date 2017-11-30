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
# <a name="icordebugsteppersetinterceptmask-method"></a>ICorDebugStepper::SetInterceptMask (Método)
Establece un valor que especifica los tipos de código que se recorren paso a paso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `mask`  
 [in] Una combinación de valores de la enumeración CorDebugIntercept que especifica los tipos de código.  
  
## <a name="remarks"></a>Comentarios  
 Si se establece el bit de un interceptor, el paso a paso desencadene se completará cuando se encuentra el tipo dado de código de intercepción. Si el bit está desactivado, se omitirá el código de intercepción.  
  
 El `SetInterceptMask` el método podría tener interacciones imprevistas con [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (desde el punto de vista del usuario). Por ejemplo, si solo visible (es decir, no interna) parte del código de inicialización de clase carece de información de asignación y STOP_NO_MAPPING_INFO no está establecido (vea la [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) método y la CorDebugUnmappedStop (enumeración)), el paso a paso desencadene recorre paso a paso sobre la inicialización de la clase. De forma predeterminada, solo el valor INTERCEPT_NONE de la `CorDebugIntercept` se usará la enumeración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
