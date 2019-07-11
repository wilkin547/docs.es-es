---
title: Método ICorDebugVariableHome::GetOffset
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fdab81d499fe1508493cb0bf05a1787974a9d01
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774530"
---
# <a name="icordebugvariablehomegetoffset-method"></a>Método ICorDebugVariableHome::GetOffset
Obtiene el desplazamiento desde el registro de base de una variable.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pOffset`  
 [out] El desplazamiento desde el registro de base.  
  
## <a name="return-value"></a>Valor devuelto  
 El método devuelve los valores siguientes:  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|`S_OK`|La variable está en una ubicación de memoria relativa del registro.|  
|`E_FAIL`|La variable no está en una ubicación de memoria relativa del registro.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugVariableHome (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
