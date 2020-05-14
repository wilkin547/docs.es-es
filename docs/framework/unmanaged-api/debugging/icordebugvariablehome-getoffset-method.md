---
title: 'ICorDebugVariableHome:: GetOffset (método)'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
ms.openlocfilehash: 75a165e2fd517f36d779a934a5bdd9c41956411a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396760"
---
# <a name="icordebugvariablehomegetoffset-method"></a>ICorDebugVariableHome:: GetOffset (método)
Obtiene el desplazamiento del registro base para una variable.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pOffset`  
 enuncia Desplazamiento del registro base.  
  
## <a name="return-value"></a>Valor devuelto  
 El método devuelve los siguientes valores:  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`S_OK`|La variable está en una ubicación de memoria relativa de registro.|  
|`E_FAIL`|La variable no está en una ubicación de memoria relativa de registro.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)
