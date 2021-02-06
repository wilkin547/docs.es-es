---
description: 'Más información sobre: ICorDebugProcess5:: Enablengenpolicy ((método)'
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
ms.openlocfilehash: 0f3194893665bfe9fff802a293aaafed8254f2e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649928"
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

 Si la Directiva se establece correctamente, el método devuelve `S_OK` . Si `ePolicy` está fuera del intervalo de los valores enumerados definidos por [cordebugngenpolicy (](cordebugngenpolicy-enumeration.md), el método devuelve `E_INVALIDARG` y la llamada al método no tiene ningún efecto. Si no se puede actualizar la Directiva del generador de imágenes nativas (Ngen.exe), el método devuelve `E_FAIL` .  
  
 `ICorDebugProcess5::EnableNGenPolicy`Se puede llamar al método en cualquier momento durante la vigencia del proceso. La Directiva está en vigor para todos los módulos que se cargan una vez establecida la Directiva.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess5 (Interfaz)](icordebugprocess5-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
