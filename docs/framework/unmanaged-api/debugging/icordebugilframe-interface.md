---
title: Interfaz ICorDebugILFrame
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
ms.openlocfilehash: 7a27b8ec512498c7bf817aca36267c37d8070a4c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788579"
---
# <a name="icordebugilframe-interface"></a>Interfaz ICorDebugILFrame

Representa un marco de pila del código del lenguaje intermedio de Microsoft (MSIL). Esta interfaz es una subclase de la interfaz ICorDebugFrame.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CanSetIP (método)](icordebugilframe-cansetip-method.md)|Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada.|  
|[EnumerateArguments (método)](icordebugilframe-enumeratearguments-method.md)|Obtiene un enumerador para los argumentos de este marco.|  
|[EnumerateLocalVariables (método)](icordebugilframe-enumeratelocalvariables-method.md)|Obtiene un enumerador para las variables locales de este marco.|  
|[GetArgument (método)](icordebugilframe-getargument-method.md)|Obtiene el valor del argumento especificado en este marco de pila de MSIL.|  
|[GetIP (método)](icordebugilframe-getip-method.md)|Obtiene el valor del puntero de instrucción y un valor de combinación bit a bit que describe cómo se obtuvo el valor del puntero de instrucción.|  
|[GetLocalVariable (método)](icordebugilframe-getlocalvariable-method.md)|Obtiene el valor de la variable local especificada en este marco de pila de MSIL.|  
|[GetStackDepth (método)](icordebugilframe-getstackdepth-method.md)|Sin implementar.|  
|[GetStackValue (método)](icordebugilframe-getstackvalue-method.md)|Sin implementar.|  
|[SetIP (método)](icordebugilframe-setip-method.md)|Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código MSIL.|  
  
## <a name="remarks"></a>Notas  
 La interfaz de `ICorDebugILFrame` es una interfaz de ICorDebugFrame especializada. Se usa para los marcos de código MSIL o para los marcos compilados Just-in-Time (JIT). Los marcos compilados JIT implementan tanto la interfaz `ICorDebugILFrame` como la interfaz ICorDebugNativeFrame.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
