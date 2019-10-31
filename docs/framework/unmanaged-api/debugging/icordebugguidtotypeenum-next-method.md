---
title: ICorDebugGuidToTypeEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
ms.openlocfilehash: f6f190cd5b2f208df5a4ed88b650af671f2e6c5c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138514"
---
# <a name="icordebugguidtotypeenumnext-method"></a>ICorDebugGuidToTypeEnum::Next (Método)
Obtiene el número especificado de instancias de [cordebugguidtotypemapping (](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) que asignan los GUID a la información de tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `celt`  
 de El número de objetos de asignación de GUID a tipo que se van a recuperar.  
  
 `values`  
 enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [cordebugguidtotypemapping (](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) que asigna un GUID Windows Runtime a su objeto ICorDebugType correspondiente.  
  
 `pceltFetched`  
 enuncia Puntero al número de objetos [cordebugguidtotypemapping (](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) realmente devueltos en `values`.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Windows Runtime  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugGuidToTypeEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
