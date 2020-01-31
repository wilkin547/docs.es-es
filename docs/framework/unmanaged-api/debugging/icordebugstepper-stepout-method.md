---
title: ICorDebugStepper::StepOut (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
ms.openlocfilehash: 08cf2d0bb09080296fc1fcc69b5817f4d6118765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791727"
---
# <a name="icordebugstepperstepout-method"></a>ICorDebugStepper::StepOut (Método)
Hace que este objeto ICorDebugStepper tenga un solo paso a través de su subproceso contenedor y que se complete cuando el fotograma actual devuelva el control al marco que realiza la llamada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>Notas  
 Una operación de `StepOut` se completará después de devolver normalmente del marco actual al marco que realiza la llamada.  
  
 Si se llama a `StepOut` en el código no administrado, el paso se completará cuando el fotograma actual vuelva al código administrado que lo llamó.  
  
 En la versión .NET Framework 2,0, no use `StepOut` con la marca STOP_UNMANAGED establecida porque se producirá un error. (Use [ICorDebugStepper:: setunmappedstopmask (](icordebugstepper-setunmappedstopmask-method.md) para establecer marcas para la ejecución paso a paso). Los depuradores de interoperabilidad deben salir del código nativo.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
