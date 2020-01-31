---
title: ICorDebugDataTarget3 (Interfaz)
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: 04e7b9a064d4a06a06b8a1518f06092ba79a3561
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783485"
---
# <a name="icordebugdatatarget3-interface"></a>ICorDebugDataTarget3 (Interfaz)
Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) para proporcionar información sobre los módulos cargados.  
  
## <a name="method"></a>Método  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetLoadedModules (método)](icordebugdatatarget3-getloadedmodules-method.md)|Obtiene una lista de los módulos que se han cargado hasta ahora.|  
  
## <a name="remarks"></a>Notas  
  
> [!NOTE]
> Esta interfaz solo está disponible con .NET Native. Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
