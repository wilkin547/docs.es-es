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
ms.openlocfilehash: 4f34fdf9a0eeb47e027cc874afee5bd04f5bd9bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712396"
---
# <a name="icordebugilframe-interface"></a>Interfaz ICorDebugILFrame

Representa un marco de pila del código del lenguaje intermedio de Microsoft (MSIL). Esta interfaz es una subclase de la interfaz ICorDebugFrame.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método CanSetIP](icordebugilframe-cansetip-method.md)|Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada.|  
|[Método EnumerateArguments](icordebugilframe-enumeratearguments-method.md)|Obtiene un enumerador para los argumentos de este marco.|  
|[Método EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md)|Obtiene un enumerador para las variables locales de este marco.|  
|[Método GetArgument](icordebugilframe-getargument-method.md)|Obtiene el valor del argumento especificado en este marco de pila de MSIL.|  
|[Método GetIP](icordebugilframe-getip-method.md)|Obtiene el valor del puntero de instrucción y un valor de combinación bit a bit que describe cómo se obtuvo el valor del puntero de instrucción.|  
|[Método GetLocalVariable](icordebugilframe-getlocalvariable-method.md)|Obtiene el valor de la variable local especificada en este marco de pila de MSIL.|  
|[Método GetStackDepth](icordebugilframe-getstackdepth-method.md)|Sin implementar.|  
|[Método GetStackValue](icordebugilframe-getstackvalue-method.md)|Sin implementar.|  
|[SetIP (Método)](icordebugilframe-setip-method.md)|Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código MSIL.|  
  
## <a name="remarks"></a>Comentarios  

 La `ICorDebugILFrame` interfaz es una interfaz de ICorDebugFrame especializada. Se usa para los marcos de código MSIL o para los marcos compilados Just-in-Time (JIT). Los marcos compilados con JIT implementan la interfaz `ICorDebugILFrame` y la interfaz ICorDebugNativeFrame.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
