---
title: 'ICorDebugVariableHome:: Getslotindex ((método)'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
ms.openlocfilehash: 4b071bd8e9d96084848c1553385eec5f8beca624
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711733"
---
# <a name="icordebugvariablehomegetslotindex-method"></a>ICorDebugVariableHome:: Getslotindex ((método)

Obtiene el índice de ranura administrado de una variable local.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pSlotIndex`  
 enuncia Puntero al índice de ranura de una variable local.  
  
## <a name="return-value"></a>Valor devuelto  

 El método devuelve los valores siguientes.  
  
|Value|Descripción|  
|-----------|-----------------|  
|`S_OK`|La llamada al método devolvió un valor de índice de ranura en `pSlotIndex` .|  
|`E_FAIL`|La instancia de [ICorDebugVariableHome](icordebugvariablehome-interface.md) actual representa un argumento de función.|  
  
## <a name="remarks"></a>Comentarios  

 Se puede usar el índice de ranura para recuperar los metadatos de esta variable local.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)
