---
title: ICorDebugAssembly (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
ms.openlocfilehash: dea3231e3bbb361b56254756c6d99b115f73e792
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133970"
---
# <a name="icordebugassembly-interface"></a>ICorDebugAssembly (Interfaz)

Representa un ensamblado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumerateModules (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|Obtiene un enumerador para los módulos incluidos en el ensamblado.|  
|[GetAppDomain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|Obtiene un puntero de interfaz al dominio de aplicación que contiene esta instancia de `ICorDebugAssembly`.|  
|[GetCodeBase (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|No se implementa en la versión actual del .NET Framework.|  
|[GetName (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|Obtiene el nombre del ensamblado.|  
|[GetProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|Obtiene la instancia de ICorDebugProcess en la que se ejecuta el ensamblado.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
