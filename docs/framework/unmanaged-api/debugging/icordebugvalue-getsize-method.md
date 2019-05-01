---
title: ICorDebugValue::GetSize (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41a9ff2c94c98a5acc930d68e648b0ea577a82c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986848"
---
# <a name="icordebugvaluegetsize-method"></a>ICorDebugValue::GetSize (Método)
Obtiene el tamaño, en bytes, de este objeto "ICorDebugValue".  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pSize`  
 [out] El tamaño, en bytes, de este objeto de valor.  
  
## <a name="remarks"></a>Comentarios  
 Si el tipo de valor es un tipo de referencia, este método devuelve el tamaño del puntero en lugar del tamaño del objeto.  
  
 El `ICorDebugValue::GetSize` devuelve del método `COR_E_OVERFLOW` para objetos que son mayores de 4 GB en plataformas de 64 bits. Use la [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) método en su lugar para los objetos que son mayores de 4 GB.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetSize64 (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
