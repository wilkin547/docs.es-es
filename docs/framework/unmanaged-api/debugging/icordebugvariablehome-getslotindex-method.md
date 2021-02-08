---
description: 'Más información sobre: ICorDebugVariableHome:: Getslotindex ((método)'
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
ms.openlocfilehash: 7f6ee01c2bfcee4c78f8463a7cefac1f90a3295f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790651"
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
  
## <a name="remarks"></a>Observaciones  

 Se puede usar el índice de ranura para recuperar los metadatos de esta variable local.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)
