---
title: 'ICorDebugModuleDebugEvent:: GetModule (método)'
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: 5dc26d0367d01bc8da957c3ce648c3e529dddb08
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096936"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a>ICorDebugModuleDebugEvent:: GetModule (método)
Obtiene el módulo combinado que se acaba de cargar o descargar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppModule`  
 enuncia Puntero a la dirección de un objeto ICorDebugModule que representa el módulo combinado que se acaba de cargar o descargar.  
  
## <a name="remarks"></a>Comentarios  
 Puede llamar al método [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) para determinar si el módulo se ha cargado o descargado.  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugModuleDebugEvent (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
