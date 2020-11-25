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
ms.openlocfilehash: 9f5688ae4f76f9ddfde231aa6252d666c9152eec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731088"
---
# <a name="icordebugvaluegetsize-method"></a>ICorDebugValue::GetSize (Método)

Obtiene el tamaño, en bytes, de este objeto "ICorDebugValue".  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pSize`  
 enuncia Tamaño, en bytes, de este objeto de valor.  
  
## <a name="remarks"></a>Comentarios  

 Si el tipo del valor es un tipo de referencia, este método devuelve el tamaño del puntero en lugar del tamaño del objeto.  
  
 El `ICorDebugValue::GetSize` método devuelve `COR_E_OVERFLOW` para objetos mayores de 4 GB en plataformas de 64 bits. Use el método [icordebugvalue3 (:: getsize64 (](icordebugvalue3-getsize64-method.md) en lugar de los objetos mayores de 4 GB.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método GetSize64](icordebugvalue3-getsize64-method.md)
