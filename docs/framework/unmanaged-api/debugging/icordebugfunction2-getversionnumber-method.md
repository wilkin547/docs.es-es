---
title: "ICorDebugFunction2::GetVersionNumber (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2.GetVersionNumber
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 37b9e34174d88be08c92c54906ebd20977dc266a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction2getversionnumber-method"></a>ICorDebugFunction2::GetVersionNumber (Método)
Obtiene la versión de editar y continuar de esta función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pnVersion`  
 [out] Un puntero a un entero que es el número de versión de la función que está representado por este objeto ICorDebugFunction2.  
  
## <a name="remarks"></a>Comentarios  
 El tiempo de ejecución realiza un seguimiento del número de modificaciones que han tenido lugar para cada módulo durante una sesión de depuración. El número de versión de una función es uno más que el número de la edición que introdujo la función. Versión original de la función es 1. El número se incrementa cada vez para un módulo [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) se llama en ese módulo. Por lo tanto, si se reemplaza el cuerpo de una función en la primera y la tercera llamada a `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` puede devolver la versión 1, 2 o 4 de esa función, pero no la versión 3. (Esa función no tendría versión 3.)  
  
 El número de versión se realiza un seguimiento por separado para cada módulo. Por lo tanto, si lleva a cabo cuatro modificaciones en el módulo 1 y ninguna en el módulo 2, la siguiente modificación en el módulo 1 asignará a un número de versión de 6 a todas las funciones modificadas en el módulo 1. Si la misma modificación afecta al módulo 2, las funciones en el módulo 2 obtendrá un número de versión de 2.  
  
 Obtiene el número de versión del `GetVersionNumber` método puede ser inferior al obtenido por [ICorDebugFunction:: GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).  
  
 El [ICorDebugCode:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) método realiza la misma operación que `ICorDebugFunction2::GetVersionNumber`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
