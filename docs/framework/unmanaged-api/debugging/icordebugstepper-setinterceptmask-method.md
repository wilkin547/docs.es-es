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
# <a name="icordebugsteppersetinterceptmask-method"></a>ICorDebugStepper::SetInterceptMask (Método)

Establece un valor que especifica los tipos de código a los que se va a recorrer.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `mask`  
 de Combinación de valores de la enumeración Cordebugintercept (que especifica los tipos de código.  
  
## <a name="remarks"></a>Observaciones  

 Si se establece el bit de un interceptor, el stepper se completará cuando se encuentre el tipo de código de interceptación especificado. Si el bit está desactivado, se omitirá el código de intercepción.  
  
 El `SetInterceptMask` método puede tener interacciones imprevistas con [ICorDebugStepper:: setunmappedstopmask (](icordebugstepper-setunmappedstopmask-method.md) (desde el punto de vista del usuario). Por ejemplo, si la única parte visible (es decir, no interna) del código de inicialización de clase no tiene información de asignación y STOP_NO_MAPPING_INFO no está establecido (vea el método [ICorDebugStepper:: setunmappedstopmask (](icordebugstepper-setunmappedstopmask-method.md) y la enumeración cordebugunmappedstop (), el stepper desplazará sobre la inicialización de la clase. De forma predeterminada, solo se utilizará el valor INTERCEPT_NONE de la `CorDebugIntercept` enumeración.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
