---
title: ICorDebugValue3::GetSize64 (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
ms.openlocfilehash: 6eb26de83a6cdce47477e6cb3dffd6a94d889975
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397024"
---
# <a name="icordebugvalue3getsize64-method"></a>ICorDebugValue3::GetSize64 (Método)
Obtiene el tamaño, en bytes, de este objeto [icordebugvalue3 (](icordebugvalue3-interface.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 pSize  
 enuncia Puntero al tamaño, en bytes, de este objeto.  
  
## <a name="remarks"></a>Comentarios  
 Si el tipo de este valor es un tipo de referencia, este método devuelve el tamaño del puntero en lugar del tamaño del objeto.  
  
 El `ICorDebugValue3::GetSize` método difiere del método [ICorDebugValue::](icordebugvalue-getsize-method.md) typeof en el tipo de su parámetro de salida. En [ICorDebugValue:: obtiene](icordebugvalue-getsize-method.md), el parámetro de salida es un `ULONG32` ; en `ICorDebugValue3::GetSize` , es un `ULONG64` . Esto permite a la interfaz [icordebugvalue3 (](icordebugvalue3-interface.md) informar del tamaño de las matrices que superan los 2 GB.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugValue3 (Interfaz)](icordebugvalue3-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
