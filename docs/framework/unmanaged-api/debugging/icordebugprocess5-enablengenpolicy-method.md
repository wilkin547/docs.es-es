---
title: ICorDebugProcess5::EnableNGENPolicy (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5::EnableNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type:
- apiref
ms.openlocfilehash: fa3cbfee0359b8477f9efe88fe72837b86611bf7
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212807"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a>ICorDebugProcess5::EnableNGENPolicy (Método)
Establece un valor que determina cómo una aplicación carga imágenes nativas mientras se ejecuta en un depurador administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ePolicy`  
 de Una constante [cordebugngenpolicy (](cordebugngenpolicy-enumeration.md) que determina cómo una aplicación carga imágenes nativas mientras se ejecuta en un depurador administrado.  
  
## <a name="remarks"></a>Observaciones  
 Si la Directiva se establece correctamente, el método devuelve `S_OK` . Si `ePolicy` está fuera del intervalo de los valores enumerados definidos por [cordebugngenpolicy (](cordebugngenpolicy-enumeration.md), el método devuelve `E_INVALIDARG` y la llamada al método no tiene ningún efecto. Si la Directiva del generador de imágenes nativas (Ngen. exe) no se puede actualizar, el método devuelve `E_FAIL` .  
  
 `ICorDebugProcess5::EnableNGenPolicy`Se puede llamar al método en cualquier momento durante la vigencia del proceso. La Directiva está en vigor para todos los módulos que se cargan una vez establecida la Directiva.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugProcess5 (Interfaz)](icordebugprocess5-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
