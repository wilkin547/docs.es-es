---
title: ICorDebugVariableHome::GetRegister (método)
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e06c98067fea9368ac8f750d9187636d2ca9a8c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugvariablehomegetregister-method"></a>ICorDebugVariableHome::GetRegister (método)
Obtiene el registro que contiene una variable con un tipo de ubicación de `VLT_REGISTER`y el registro de base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pRegister`  
 [out] Un valor de enumeración de CorDebugRegister que indica el registro de una variable con un tipo de ubicación de `VLT_REGISTER`y el registro de base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.  
  
## <a name="return-value"></a>Valor devuelto  
 El método devuelve los siguientes valores:  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`S_OK`|La variable está en el registro indicado por la `pRegister` argumento.|  
|`E_FAIL`|La variable no está en un registro o una ubicación relativa del registro.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [VariableLocationType (enumeración)](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 [ICorDebugVariableHome (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
