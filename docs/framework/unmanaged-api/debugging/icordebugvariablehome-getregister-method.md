---
title: 'ICorDebugVariableHome:: GetRegister (método)'
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
ms.openlocfilehash: 396dd9c017fca6dc7037b43355ba7f726d7390ea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790986"
---
# <a name="icordebugvariablehomegetregister-method"></a>ICorDebugVariableHome:: GetRegister (método)
Obtiene el registro que contiene una variable con un tipo de ubicación de `VLT_REGISTER`y el registro base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pRegister`  
 enuncia Un valor de enumeración CorDebugRegister (que indica el registro de una variable con un tipo de ubicación de `VLT_REGISTER`y el registro base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE`.  
  
## <a name="return-value"></a>Valor devuelto  
 El método devuelve los siguientes valores:  
  
|{2&gt;Value&lt;2}|Descripción|  
|-----------|-----------------|  
|`S_OK`|La variable está en el registro indicado por el argumento `pRegister`.|  
|`E_FAIL`|La variable no está en un registro o en una ubicación relativa del registro.|  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [VariableLocationType (enumeración)](variablelocationtype-enumeration.md)
- [ICorDebugVariableHome (interfaz)](icordebugvariablehome-interface.md)
