---
title: ICorDebugILFrame4 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame4
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type:
- apiref
ms.openlocfilehash: 010d73309ae21f9a593f72533691bdd95fbd4132
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130849"
---
# <a name="icordebugilframe4-interface"></a>ICorDebugILFrame4 (Interfaz)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL). Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumerateLocalVariablesEx (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)|Devuelve una lista de las variables locales disponibles en el marco actual.|  
|[GetCodeEx (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)|Devuelve el código que este marco de pila está ejecutando.|  
|[GetLocalVariableEx (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)|Devuelve el valor de una variable local en el marco de IL.|  
  
## <a name="remarks"></a>Comentarios  
 Estos métodos ofrecen funcionalidad además de la que proporcionan los métodos [enumeratelocalvariables (](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [getCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)y [getlocalvariable (](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) . Cada método incluye un parámetro `flags` que especifica si otras variables locales o código definidos por una solicitud ReJIT del generador de perfiles son visibles.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
