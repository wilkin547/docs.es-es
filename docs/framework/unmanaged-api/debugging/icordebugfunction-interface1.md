---
title: ICorDebugFunction (Interfaz)
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
ms.openlocfilehash: eb2b1e218314be01898ce90c4378fb713f9bf6ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137849"
---
# <a name="icordebugfunction-interface"></a>ICorDebugFunction (Interfaz)

Representa una función o un método administrado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateBreakpoint (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|Crea un punto de interrupción al principio de esta función.|  
|[GetClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|Obtiene un objeto ICorDebugClass que representa la clase de la que es miembro esta función.|  
|[GetCurrentVersionNumber (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|Obtiene el número de versión de la edición más reciente realizada en esta función.|  
|[GetILCode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|Obtiene el código del lenguaje intermedio de Microsoft (MSIL) de esta función.|  
|[GetLocalVarSigToken (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|Obtiene el símbolo (token) de metadatos de la firma de variable local de la función representada por esta instancia de `ICorDebugFunction`.|  
|[GetModule (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Obtiene el módulo en el que se define esta función.|  
|[GetNativeCode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|Obtiene el código nativo de esta función.|  
|[GetToken (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|Obtiene el símbolo (token) de metadatos de esta función.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz `ICorDebugFunction` no representa una función con parámetros de tipo genérico. Por ejemplo, una instancia de `ICorDebugFunction` representaría `Func<T>` pero no `Func<string>`. Llame a [ICorDebugILFrame2:: EnumerateTypeParameters (](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) para obtener los parámetros de tipo genérico.  
  
 La relación entre el símbolo (token) de metadatos de un método, `mdMethodDef`y el objeto `ICorDebugFunction` de un método depende de si se permite editar y continuar en la función:  
  
- Si no se permite editar y continuar en la función, existe una relación uno a uno entre el objeto de `ICorDebugFunction` y el token de `mdMethodDef`. Es decir, la función tiene un objeto `ICorDebugFunction` y un token `mdMethodDef`.  
  
- Si se permite editar y continuar en la función, existe una relación de varios a uno entre el objeto de `ICorDebugFunction` y el token de `mdMethodDef`. Es decir, la función puede tener muchas instancias de `ICorDebugFunction`, una para cada versión de la función, pero solo un token de `mdMethodDef`.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:**  CorGuids. lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
