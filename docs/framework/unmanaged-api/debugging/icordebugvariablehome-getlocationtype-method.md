---
title: 'ICorDebugVariableHome:: GetLocationType (método)'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
ms.openlocfilehash: 3979ed19f8a61ac1fc045b83c52e23d7255ac364
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711876"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a>ICorDebugVariableHome:: GetLocationType (método)

Obtiene el tipo de la ubicación nativa de la variable.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pLocationType`  
 enuncia Puntero al tipo de la ubicación nativa de la variable.  Vea la enumeración [VariableLocationType](variablelocationtype-enumeration.md) para obtener más información.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)
- [Enumeración VariableLocationType](variablelocationtype-enumeration.md)
