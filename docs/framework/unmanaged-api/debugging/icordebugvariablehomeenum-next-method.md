---
title: Método ICorDebugVariableHomeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d383d4bf0f3d203c331ff00981885cbc6c0c35d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519208"
---
# <a name="icordebugvariablehomeenumnext-method"></a>Método ICorDebugVariableHomeEnum::Next
Obtiene el número especificado de [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instancias que contienen información sobre las variables locales y los argumentos en una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `celt`  
 [in] Número de objetos que se van a recuperar.  
  
 `homes`  
 Una matriz de punteros, cada uno de los cuales señala a un [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objeto que proporciona información sobre una variable local o argumento de una función.  
  
 `pceltFetched`  
 [out] El número de instancias realmente devueltos en los objetos.  
  
## <a name="return-value"></a>Valor devuelto  
 El método devuelve los valores siguientes.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|El método se completó correctamente.|  
|`S_FALSE`|Recupera el número real de las instancias, tal como se refleja en `pceltFetched`, es menor que el número de instancias solicitadas.|  
  
## <a name="remarks"></a>Comentarios  
 El [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) método recupera un máximo de `celt` objetos que comienza en la posición actual del enumerador. Cuando el método vuelve, `pceltFetched` contiene el número real de los objetos recuperados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorDebugVariableHomeEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
- [ICorDebugVariableHome (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
