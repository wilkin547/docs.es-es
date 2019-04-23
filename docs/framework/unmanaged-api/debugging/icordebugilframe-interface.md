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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c60d7685de1e9a1d4f631ad1fba53b981829f58
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159807"
---
# <a name="icordebugilframe-interface"></a>Interfaz ICorDebugILFrame

Representa un marco de pila del código de lenguaje intermedio (MSIL) de Microsoft. Esta interfaz es una subclase de ICorDebugFrame (interfaz).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CanSetIP (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada.|  
|[EnumerateArguments (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|Obtiene un enumerador para los argumentos de este marco.|  
|[EnumerateLocalVariables (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|Obtiene un enumerador para las variables locales de este marco.|  
|[GetArgument (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|Obtiene el valor del argumento especificado en este marco de pila MSIL.|  
|[GetIP (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|Obtiene el valor del puntero de instrucción y un valor de combinación bit a bit que se describe cómo se obtuvo el valor del puntero de instrucción.|  
|[GetLocalVariable (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|Obtiene el valor de la variable local especificada en este marco de pila MSIL.|  
|[GetStackDepth (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|Sin implementar.|  
|[GetStackValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|Sin implementar.|  
|[SetIP (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código MSIL.|  
  
## <a name="remarks"></a>Comentarios  
 El `ICorDebugILFrame` trata de una interfaz ICorDebugFrame especializada. Se utiliza para los marcos de código MSIL o just-in-Time (JIT) compila marcos. Los marcos de la compilación JIT implementan tanto el `ICorDebugILFrame` interfaz y ICorDebugNativeFrame (interfaz).  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
