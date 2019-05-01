---
title: ICorDebugFunction2::GetVersionNumber (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cc9c2af62184c83857b82445941f6087a05c2c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995618"
---
# <a name="icordebugfunction2getversionnumber-method"></a>ICorDebugFunction2::GetVersionNumber (Método)
Obtiene la versión de editar y continuar de esta función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pnVersion`  
 [out] Un puntero a un entero que es el número de versión de la función representada por este objeto ICorDebugFunction2.  
  
## <a name="remarks"></a>Comentarios  
 El tiempo de ejecución realiza un seguimiento de la cantidad de modificaciones que han tenido lugar para cada módulo durante una sesión de depuración. El número de versión de una función es uno más que el número de la edición que introdujo la función. Versión original de la función es 1. El número se incrementa cada vez para un módulo [Icordebugmodule2](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) se llama en ese módulo. Por lo tanto, si se ha reemplazado el cuerpo de una función en la primera y tercera llamada a `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` puede devolver la versión 1, 2 ó 4 para esa función, pero no la versión 3. (Esa función no tendría ninguna versión 3).  
  
 El número de versión se realiza un seguimiento por separado para cada módulo. Por lo tanto, si realizar cuatro modificaciones en el módulo 1 y ninguna en el módulo 2, la siguiente modificación en el módulo 1 asignará a un número de versión de 6 a todas las funciones modificadas en el módulo 1. Si la misma modificación afecta al módulo 2, las funciones del módulo 2 obtendrá un número de versión 2.  
  
 Obtiene el número de versión por el `GetVersionNumber` método puede ser inferior al que obtiene al [ICorDebugFunction:: GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).  
  
 El [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) método realiza la misma operación que `ICorDebugFunction2::GetVersionNumber`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
