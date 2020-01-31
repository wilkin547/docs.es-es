---
title: ICorDebugBlockingObjectEnum::Next (método)
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
ms.openlocfilehash: c25f26bb0f1f34e3799bab4bec7e697d393cccb4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784511"
---
# <a name="icordebugblockingobjectenumnext-method"></a>ICorDebugBlockingObjectEnum::Next (método)
Obtiene el número especificado de objetos [CorDebugBlockingObject](cordebugblockingobject-structure.md) de la enumeración, comenzando en la posición actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a>Parameters  
 `celt`  
 de Número de objetos que se van a recuperar.  
  
 `values`  
 enuncia Matriz de punteros a objetos [CorDebugBlockingObject](cordebugblockingobject-structure.md) .  
  
 `pceltFetched`  
 enuncia Puntero al número de objetos recuperados.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT concretos.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|S_FALSE|`pceltFetched` no es igual a `celt`.|  
  
## <a name="remarks"></a>Notas  
 Este método funciona como un enumerador COM típico.  
  
 Los valores de la matriz de entrada deben tener al menos el tamaño `celt`. La matriz se rellenará con los valores de `celt` siguientes en la enumeración o con todos los valores restantes si se mantiene menos de `celt`. Cuando este método devuelve un valor, `pceltFetched` se rellenará con el número de valores recuperados. Si `values` contiene punteros no válidos o apunta a un búfer menor que `celt`, o si `pceltFetched` es un puntero no válido, el resultado es indefinido.  
  
> [!NOTE]
> Aunque no es necesario liberar la estructura [CorDebugBlockingObject](cordebugblockingobject-structure.md) , es necesario liberar la interfaz "ICorDebugValue" dentro de ella.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugDataTarget (interfaz)](icordebugdatatarget-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
