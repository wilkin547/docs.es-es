---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dde27f74ac59d033b6e25fba1dbb8e52c4b91af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760680"
---
# <a name="icordebugstepperisactive-method"></a>ICorDebugStepper::IsActive (Método)
Obtiene un valor que indica si esta instancia de ICorDebugStepper está ejecutando actualmente un paso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbActive`  
 [out] Devuelve `true` si el componente se está ejecutando actualmente un paso; de lo contrario, devuelve `false`.  
  
## <a name="remarks"></a>Comentarios  
 Cualquier acción paso permanece activa hasta que el depurador recibe un [StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) llamar, que desactiva automáticamente el motor paso a paso. Un motor paso a paso también se puede desactivar prematuramente mediante una llamada a [ICorDebugStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) antes de la devolución de llamada se alcanza la condición.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
