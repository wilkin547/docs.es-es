---
title: Interfaz ICorDebugFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae65c59efe1d925b5e058e8664d1e093fdfec875
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917202"
---
# <a name="icordebugfunction-interface"></a>Interfaz ICorDebugFunction

Representa una función o un método administrado.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|[CreateBreakpoint (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|Crea un punto de interrupción al principio de esta función.|  
|[GetClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|Obtiene un objeto ICorDebugClass que representa la clase de la que es miembro esta función.|  
|[GetCurrentVersionNumber (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|Obtiene el número de versión de la edición más reciente realizada en esta función.|  
|[GetILCode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|Obtiene el código del lenguaje intermedio de Microsoft (MSIL) de esta función.|  
|[GetLocalVarSigToken (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|Obtiene el símbolo (token) de metadatos de la firma de variable local de la `ICorDebugFunction` función representada por esta instancia.|  
|[GetModule (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Obtiene el módulo en el que se define esta función.|  
|[GetNativeCode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|Obtiene el código nativo de esta función.|  
|[GetToken (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|Obtiene el símbolo (token) de metadatos de esta función.|  
  
## <a name="remarks"></a>Comentarios  
 La `ICorDebugFunction` interfaz no representa una función con parámetros de tipo genérico. Por ejemplo, una `ICorDebugFunction` instancia de representaría `Func<string>` `Func<T>` pero no. Llame a [ICorDebugILFrame2:: EnumerateTypeParameters (](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) para obtener los parámetros de tipo genérico.  
  
 La relación entre el token de metadatos de `mdMethodDef`un método,, y `ICorDebugFunction` el objeto de un método depende de si se permite editar y continuar en la función:  
  
- Si no se permite editar y continuar en la función, existe una relación uno a uno entre el `ICorDebugFunction` objeto y el `mdMethodDef` token. Es decir, la función tiene un `ICorDebugFunction` objeto y un `mdMethodDef` token.  
  
- Si se permite editar y continuar en la función, existe una relación de varios a uno entre el `ICorDebugFunction` objeto y el `mdMethodDef` token. Es decir, la función puede tener muchas instancias de `ICorDebugFunction`, una por cada versión de la función, pero solo un `mdMethodDef` token.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cordebug. idl, Cordebug. h  
  
 **Biblioteca**  CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
