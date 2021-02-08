---
description: 'Más información acerca de: ICorDebugModuleDebugEvent:: GetModule (método)'
title: Método ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: c6d7171da231576ff90f54aaefe4b473af0afd40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790742"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a>Método ICorDebugModuleDebugEvent::GetModule

Obtiene el módulo combinado que se acaba de cargar o descargar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppModule`  
 [out] Puntero a la dirección de un objeto ICorDebugModule que representa el módulo de combinación que se acaba de cargar o descargar.  
  
## <a name="remarks"></a>Observaciones  

 Puede llamar al método [GetEventKind](icordebugdebugevent-geteventkind-method.md) para determinar si el módulo se ha cargado o descargado.  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
