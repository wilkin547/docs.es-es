---
description: 'Más información acerca de: ICorDebugStepper:: IsActive (método)'
title: ICorDebugStepper::IsActive (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
ms.openlocfilehash: 7ef937ac3c1e6f3ad9ad83b5fa84382cac3ac9c1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803573"
---
# <a name="icordebugstepperisactive-method"></a>ICorDebugStepper::IsActive (Método)

Obtiene un valor que indica si esta ICorDebugStepper está ejecutando actualmente un paso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pbActive`  
 enuncia Devuelve `true` si el stepper está ejecutando actualmente un paso; de lo contrario, devuelve `false` .  
  
## <a name="remarks"></a>Observaciones  

 Cualquier acción de paso permanece activa hasta que el depurador recibe una llamada [ICorDebugManagedCallback:: StepComplete (](icordebugmanagedcallback-stepcomplete-method.md) , que desactiva automáticamente el stepper. Un stepper también se puede desactivar prematuramente si se llama a [ICorDebugStepper::D eactivate](icordebugstepper-deactivate-method.md) antes de que se alcance la condición de devolución de llamada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
