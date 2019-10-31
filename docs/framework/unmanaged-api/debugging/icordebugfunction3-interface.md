---
title: ICorDebugFunction3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: fc50fd7180aaf5c1cff2147268d34921eec39e8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137761"
---
# <a name="icordebugfunction3-interface"></a>ICorDebugFunction3 (Interfaz)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Extiende lógicamente la interfaz ICorDebugFunction para proporcionar acceso al código desde una solicitud ReJIT.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetActiveReJitRequestILCode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|Obtiene un puntero de interfaz a un [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) que contiene el Il de una solicitud ReJIT activa.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [ReJIT: Guía de procedimientos](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
