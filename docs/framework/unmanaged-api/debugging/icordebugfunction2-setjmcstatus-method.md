---
title: ICorDebugFunction2::SetJMCStatus (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67959b2ebbfb62b47a1b2a770e278d043fc66d21
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754920"
---
# <a name="icordebugfunction2setjmcstatus-method"></a>ICorDebugFunction2::SetJMCStatus (Método)
Marca la función representada por este ICorDebugFunction2 solo mi código para la ejecución paso a paso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `bIsJustMyCode`  
 [in] Establecido en `true` para marcar la función como código de usuario; de lo contrario, establézcalo en `false`.  
  
## <a name="return-values"></a>Valores devueltos  
  
|HRESULT|DESCRIPCIÓN|  
|-------------|-----------------|  
|`S_OK`|La función se ha marcado correctamente.|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|La función no se pudieron marcar como código de usuario porque no se pueden depurar.|  
  
## <a name="remarks"></a>Comentarios  
 Un motor paso a paso solo mi código omitirá el código de no usuario. Código de usuario debe ser un subconjunto del código depurable.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
