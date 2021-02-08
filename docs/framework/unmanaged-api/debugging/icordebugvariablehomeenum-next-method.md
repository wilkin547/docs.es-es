---
description: 'Más información sobre: ICorDebugVariableHomeEnum:: Next (método)'
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
ms.openlocfilehash: 0aa0174e67bceaa724ddfeadc2560d12e112b859
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790612"
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
  
## <a name="parameters"></a>Parámetros  

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
|`S_FALSE`|El número real de instancias recuperadas, como se refleja en `pceltFetched` , es menor que el número de instancias solicitadas.|  
  
## <a name="remarks"></a>Observaciones  

 El método [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) recupera un máximo de  `celt` objetos a partir de la posición actual del enumerador. Cuando el método vuelve, `pceltFetched` contiene el número real de objetos recuperados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)
- [Interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)
