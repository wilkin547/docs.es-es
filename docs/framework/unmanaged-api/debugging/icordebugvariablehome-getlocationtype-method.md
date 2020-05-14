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
ms.openlocfilehash: 8874deede8b46b93df0e298fb3970fa153b51415
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396573"
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
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)
- [Enumeración VariableLocationType](variablelocationtype-enumeration.md)
