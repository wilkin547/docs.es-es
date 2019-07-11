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
# <a name="icordebugsteppersetinterceptmask-method"></a>ICorDebugStepper::SetInterceptMask (Método)
Establece un valor que especifica los tipos de código que se ejecutar paso a paso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `mask`  
 [in] Una combinación de valores de la enumeración CorDebugIntercept que especifica los tipos de código.  
  
## <a name="remarks"></a>Comentarios  
 Si se establece el bit de un interceptor, el motor paso a paso se completará cuando se encuentra el tipo especificado de interceptar el código. Si el bit está desactivado, se omitirá el código de intercepción.  
  
 El `SetInterceptMask` método puede tener interacciones imprevistas con [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (desde el punto de vista del usuario). Por ejemplo, si solo está visible (es decir, no interna) parte del código de inicialización de clase carece de información de asignación y STOP_NO_MAPPING_INFO no está establecido (consulte la [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) método y el CorDebugUnmappedStop (enumeración)), el motor paso a paso le guiará a través de la inicialización de clase. De forma predeterminada, solo el valor INTERCEPT_NONE de la `CorDebugIntercept` se usará la enumeración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
