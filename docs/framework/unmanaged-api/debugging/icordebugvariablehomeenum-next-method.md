---
title: 'ICorDebugVariableHomeEnum:: Next (método)'
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
ms.openlocfilehash: 2bb6fee00bb99555bc19f35e1250880cc3985f7f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790938"
---
# <a name="icordebugvariablehomeenumnext-method"></a>ICorDebugVariableHomeEnum:: Next (método)
Obtiene el número especificado de instancias de [ICorDebugVariableHome](icordebugvariablehome-interface.md) que contienen información sobre las variables locales y los argumentos de una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `celt`  
 [in] Número de objetos que se van a recuperar.  
  
 `homes`  
 Una matriz de punteros, cada uno de los cuales apunta a un objeto [ICorDebugVariableHome](icordebugvariablehome-interface.md) que proporciona información acerca de una variable local o un argumento de una función.  
  
 `pceltFetched`  
 enuncia Número de instancias devueltas realmente en objetos.  
  
## <a name="return-value"></a>Valor devuelto  
 El método devuelve los valores siguientes.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|El método se completó correctamente.|  
|`S_FALSE`|El número real de instancias recuperadas, como se refleja en `pceltFetched`, es menor que el número de instancias solicitadas.|  
  
## <a name="remarks"></a>Notas  
 El método [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) recupera un máximo de `celt` objetos que comienzan en la posición actual del enumerador. Cuando el método devuelve un valor, `pceltFetched` contiene el número real de objetos recuperados.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugVariableHomeEnum (interfaz)](icordebugvariablehomeenum-interface.md)
- [ICorDebugVariableHome (interfaz)](icordebugvariablehome-interface.md)
