---
title: ICorDebugFunction Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction
helpviewer_keywords: ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 327ef9f74e94e3b1b20e78eb6a833038b5bfe16d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction-interface1"></a>ICorDebugFunction Interfaz1
Representa una función o un método administrado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateBreakpoint (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|Crea un punto de interrupción al principio de esta función.|  
|[GetClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|Obtiene un objeto ICorDebugClass que representa la clase de de que esta función es un miembro.|  
|[GetCurrentVersionNumber (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|Obtiene el número de versión de la edición más reciente realizada en esta función.|  
|[GetILCode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|Obtiene el código de lenguaje intermedio (MSIL) de Microsoft para esta función.|  
|[GetLocalVarSigToken (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|Obtiene los metadatos del token para la firma de variable local de la función que está representada por este `ICorDebugFunction` instancia.|  
|[GetModule (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Obtiene el módulo en el que se define esta función.|  
|[GetNativeCode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|Obtiene el código nativo para esta función.|  
|[GetToken (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|Obtiene los metadatos del token para esta función.|  
  
## <a name="remarks"></a>Comentarios  
 El `ICorDebugFunction` interfaz no representa una función con parámetros de tipo genérico. Por ejemplo, un `ICorDebugFunction` representaría instancia `Func<T>` pero no `Func<string>`. Llame a [ICorDebugILFrame2:: EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) para obtener los parámetros de tipo genérico.  
  
 La relación entre el token de metadatos de un método `mdMethodDef`y un método `ICorDebugFunction` objeto depende de si se permite editar y continuar en la función:  
  
-   Si no se permite editar y continuar en la función, existe una relación uno a uno entre el `ICorDebugFunction` objeto y el `mdMethodDef` símbolo (token). Es decir, la función tiene una `ICorDebugFunction` objeto y otro `mdMethodDef` símbolo (token).  
  
-   Si se permite editar y continuar en la función, existe una relación de varios a uno entre el `ICorDebugFunction` objeto y el `mdMethodDef` símbolo (token). Es decir, la función puede tener muchas instancias de `ICorDebugFunction`, uno para cada versión de la función, pero solo uno `mdMethodDef` símbolo (token).  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
