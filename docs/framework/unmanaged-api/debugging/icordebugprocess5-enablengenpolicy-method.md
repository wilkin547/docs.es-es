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
ms.openlocfilehash: 583819e8e7ab16a8ac1ce72892f4353e3043ce3d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129697"
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
 de Una constante [cordebugngenpolicy (](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) que determina cómo una aplicación carga imágenes nativas mientras se ejecuta en un depurador administrado.  
  
## <a name="remarks"></a>Comentarios  
 Si la Directiva se establece correctamente, el método devuelve `S_OK`. Si `ePolicy` está fuera del intervalo de valores enumerados definidos por [cordebugngenpolicy (](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), el método devuelve `E_INVALIDARG` y la llamada al método no tiene ningún efecto. Si la Directiva del generador de imágenes nativas (Ngen. exe) no se puede actualizar, el método devuelve `E_FAIL`.  
  
 Se puede llamar al método `ICorDebugProcess5::EnableNGenPolicy` en cualquier momento durante la vigencia del proceso. La Directiva está en vigor para todos los módulos que se cargan una vez establecida la Directiva.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess5 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
