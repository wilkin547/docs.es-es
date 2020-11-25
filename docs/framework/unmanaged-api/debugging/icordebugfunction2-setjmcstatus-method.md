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
ms.openlocfilehash: 55f219b5b834f365b87440e69bfa7d2c4e519235
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696102"
---
# <a name="icordebugfunction2setjmcstatus-method"></a>ICorDebugFunction2::SetJMCStatus (Método)

Marca la función representada por este ICorDebugFunction2 para Solo mi código Stepping.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `bIsJustMyCode`  
 de Establezca en `true` para marcar la función como código de usuario; de lo contrario, establézcalo en `false` .  
  
## <a name="return-values"></a>Valores devueltos  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|La función se marcó correctamente.|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|No se pudo marcar la función como código de usuario porque no se puede depurar.|  
  
## <a name="remarks"></a>Comentarios  

 Una Solo mi código stepper omitirá el código que no es de usuario. El código de usuario debe ser un subconjunto del código depurable.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
