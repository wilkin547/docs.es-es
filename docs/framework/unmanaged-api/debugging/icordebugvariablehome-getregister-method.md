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
ms.openlocfilehash: 7f912f4b13620b567f5aa097604e98112d85f02d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711759"
---
# <a name="icordebugvariablehomegetregister-method"></a>ICorDebugVariableHome:: GetRegister (método)

Obtiene el registro que contiene una variable con un tipo de ubicación de `VLT_REGISTER` y el registro base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE` .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pRegister`  
 enuncia Un valor de enumeración CorDebugRegister (que indica el registro de una variable con un tipo de ubicación de `VLT_REGISTER` y el registro base de una variable con un tipo de ubicación de `VLT_REGISTER_RELATIVE` .  
  
## <a name="return-value"></a>Valor devuelto  

 El método devuelve los siguientes valores:  
  
|Value|Descripción|  
|-----------|-----------------|  
|`S_OK`|La variable está en el registro indicado por el `pRegister` argumento.|  
|`E_FAIL`|La variable no está en un registro o en una ubicación relativa del registro.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeración VariableLocationType](variablelocationtype-enumeration.md)
- [Interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)
