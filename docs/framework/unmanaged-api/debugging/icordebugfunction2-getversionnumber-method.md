---
description: 'Más información acerca de: ICorDebugFunction2:: GetVersionNumber ((método)'
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
ms.openlocfilehash: 7a703789099b82121c65214d6b1929e354405c8d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692217"
---
# <a name="icordebugfunction2getversionnumber-method"></a>ICorDebugFunction2::GetVersionNumber (Método)

Obtiene la versión de edición y continuación de esta función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pnVersion`  
 enuncia Un puntero a un entero que es el número de versión de la función representada por este objeto ICorDebugFunction2.  
  
## <a name="remarks"></a>Observaciones  

 El tiempo de ejecución realiza un seguimiento del número de modificaciones que se han producido en cada módulo durante una sesión de depuración. El número de versión de una función es uno más que el número de la edición que presentó la función. La versión original de la función es la versión 1. El número se incrementa para un módulo cada vez que se llama a [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md) en ese módulo. Por lo tanto, si el cuerpo de una función se ha reemplazado en la primera y la tercera llamada a `ICorDebugModule2::ApplyChanges` , `GetVersionNumber` puede devolver la versión 1, 2 o 4 para esa función, pero no la versión 3. (Esa función no tendría la versión 3).  
  
 Se realiza un seguimiento del número de versión por separado para cada módulo. Por lo tanto, si realiza cuatro ediciones en el módulo 1 y ninguna en el módulo 2, la siguiente edición del módulo 1 asignará un número de versión de 6 a todas las funciones editadas en el módulo 1. Si la misma edición toca el módulo 2, las funciones del módulo 2 obtendrán un número de versión de 2.  
  
 El número de versión obtenido por el `GetVersionNumber` método puede ser menor que el obtenido por [ICorDebugFunction:: GetCurrentVersionNumber (](icordebugfunction-getcurrentversionnumber-method.md).  
  
 El método [ICorDebugCode:: GetVersionNumber (](icordebugcode-getversionnumber-method.md) realiza la misma operación que `ICorDebugFunction2::GetVersionNumber` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
