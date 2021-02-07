---
description: 'Más información sobre: ICorDebugFunction (interfaz)'
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
ms.openlocfilehash: 835625341889e89e15ceb66ca71531cf7b8311c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692399"
---
# <a name="icordebugfunction-interface"></a>Interfaz ICorDebugFunction

Representa una función o un método administrado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método CreateBreakpoint](icordebugfunction-createbreakpoint-method.md)|Crea un punto de interrupción al principio de esta función.|  
|[Método GetClass](icordebugfunction-getclass-method.md)|Obtiene un objeto ICorDebugClass que representa la clase de la que es miembro esta función.|  
|[Método GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md)|Obtiene el número de versión de la edición más reciente realizada en esta función.|  
|[Método GetILCode](icordebugfunction-getilcode-method.md)|Obtiene el código del lenguaje intermedio de Microsoft (MSIL) de esta función.|  
|[GetLocalVarSigToken (Método)](icordebugfunction-getlocalvarsigtoken-method.md)|Obtiene el símbolo (token) de metadatos de la firma de variable local de la función representada por esta `ICorDebugFunction` instancia.|  
|[GetModule (Método)](icordebugfunction-getmodule-method.md)|Obtiene el módulo en el que se define esta función.|  
|[Método GetNativeCode](icordebugfunction-getnativecode-method.md)|Obtiene el código nativo de esta función.|  
|[GetToken (Método)](icordebugfunction-gettoken-method.md)|Obtiene el símbolo (token) de metadatos de esta función.|  
  
## <a name="remarks"></a>Observaciones  

 La `ICorDebugFunction` interfaz no representa una función con parámetros de tipo genérico. Por ejemplo, una `ICorDebugFunction` instancia de representaría `Func<T>` pero no `Func<string>` . Llame a [ICorDebugILFrame2:: EnumerateTypeParameters (](icordebugilframe2-enumeratetypeparameters-method.md) para obtener los parámetros de tipo genérico.  
  
 La relación entre el token de metadatos de un método, `mdMethodDef` , y el objeto de un método `ICorDebugFunction` depende de si se permite editar y continuar en la función:  
  
- Si no se permite editar y continuar en la función, existe una relación uno a uno entre el `ICorDebugFunction` objeto y el `mdMethodDef` token. Es decir, la función tiene un `ICorDebugFunction` objeto y un `mdMethodDef` token.  
  
- Si se permite editar y continuar en la función, existe una relación de varios a uno entre el `ICorDebugFunction` objeto y el `mdMethodDef` token. Es decir, la función puede tener muchas instancias de `ICorDebugFunction` , una por cada versión de la función, pero solo un `mdMethodDef` token.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:**  CorGuids. lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
