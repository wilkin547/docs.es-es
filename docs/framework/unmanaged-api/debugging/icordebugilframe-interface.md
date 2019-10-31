---
title: ICorDebugILFrame (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
ms.openlocfilehash: 01c247f838f66d1a77831755126a5a1f56870c1e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095142"
---
# <a name="icordebugilframe-interface"></a>ICorDebugILFrame (Interfaz)

Representa un marco de pila del código del lenguaje intermedio de Microsoft (MSIL). Esta interfaz es una subclase de la interfaz ICorDebugFrame.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CanSetIP (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada.|  
|[EnumerateArguments (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|Obtiene un enumerador para los argumentos de este marco.|  
|[EnumerateLocalVariables (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|Obtiene un enumerador para las variables locales de este marco.|  
|[GetArgument (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|Obtiene el valor del argumento especificado en este marco de pila de MSIL.|  
|[GetIP (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|Obtiene el valor del puntero de instrucción y un valor de combinación bit a bit que describe cómo se obtuvo el valor del puntero de instrucción.|  
|[GetLocalVariable (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|Obtiene el valor de la variable local especificada en este marco de pila de MSIL.|  
|[GetStackDepth (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|Sin implementar.|  
|[GetStackValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|Sin implementar.|  
|[SetIP (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código MSIL.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz de `ICorDebugILFrame` es una interfaz de ICorDebugFrame especializada. Se usa para los marcos de código MSIL o para los marcos compilados Just-in-Time (JIT). Los marcos compilados JIT implementan tanto la interfaz `ICorDebugILFrame` como la interfaz ICorDebugNativeFrame.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
