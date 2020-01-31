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
ms.openlocfilehash: a6f93ec3c7ffe415c41dcf094dbde2f0a08969f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790998"
---
# <a name="icordebugvariablehomegetoffset-method"></a>ICorDebugVariableHome:: GetOffset (método)
Obtiene el desplazamiento del registro base para una variable.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pOffset`  
 enuncia Desplazamiento del registro base.  
  
## <a name="return-value"></a>Valor devuelto  
 El método devuelve los siguientes valores:  
  
|{2&gt;Value&lt;2}|Descripción|  
|-----------|-----------------|  
|`S_OK`|La variable está en una ubicación de memoria relativa de registro.|  
|`E_FAIL`|La variable no está en una ubicación de memoria relativa de registro.|  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugVariableHome (interfaz)](icordebugvariablehome-interface.md)
