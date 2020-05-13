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
ms.openlocfilehash: d0b1c31d45efea4892182c43c801112530361994
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213707"
---
# <a name="icordebugilframe4-interface"></a>ICorDebugILFrame4 (Interfaz)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL). Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumerateLocalVariablesEx (método)](icordebugilframe4-enumeratelocalvariablesex-method.md)|Devuelve una lista de las variables locales disponibles en el marco actual.|  
|[GetCodeEx (método)](icordebugilframe4-getcodeex-method.md)|Devuelve el código que este marco de pila está ejecutando.|  
|[GetLocalVariableEx (método)](icordebugilframe4-getlocalvariableex-method.md)|Devuelve el valor de una variable local en el marco de IL.|  
  
## <a name="remarks"></a>Observaciones  
 Estos métodos ofrecen funcionalidad además de la que proporcionan los métodos [enumeratelocalvariables (](icordebugilframe-enumeratelocalvariables-method.md), [getCode](icordebugframe-getcode-method.md)y [getlocalvariable (](icordebugilframe-getlocalvariable-method.md) . Cada método incluye un parámetro `flags` que especifica si otras variables locales o código definidos por una solicitud ReJIT del generador de perfiles son visibles.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
