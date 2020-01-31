---
title: Interfaz ICorDebugEval2
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
ms.openlocfilehash: e69b32430651edd0222db874e2659bd959f89549
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788710"
---
# <a name="icordebugeval2-interface"></a>Interfaz ICorDebugEval2

Extiende "ICorDebugEval" para proporcionar compatibilidad con los tipos genéricos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CallParameterizedFunction (método)](icordebugeval2-callparameterizedfunction-method.md)|Configura una llamada a la instrucción "ICorDebugFunction" especificada, que puede estar anidada dentro de un tipo cuyo constructor toma parámetros de tipo, o bien puede tomar parámetros de tipo.|  
|[CreateValueForType (método)](icordebugeval2-createvaluefortype-method.md)|Obtiene un puntero a una nueva expresión "ICorDebugValue" del tipo especificado, con un valor inicial de null o cero.|  
|[NewParameterizedArray (método)](icordebugeval2-newparameterizedarray-method.md)|Asigna una nueva matriz del tipo de elemento y las dimensiones especificadas.|  
|[NewParameterizedObject (método)](icordebugeval2-newparameterizedobject-method.md)|Crea una instancia de un nuevo objeto de tipo parametrizado y llama al método de constructor del objeto.|  
|[NewParameterizedObjectNoConstructor (método)](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|Crea una instancia de un nuevo objeto de tipo parametrizado de la clase especificada sin intentar llamar a un método de constructor.|  
|[NewStringWithLength (método)](icordebugeval2-newstringwithlength-method.md)|Crea una nueva cadena de la longitud especificada con el contenido especificado.|  
|[RudeAbort (método)](icordebugeval2-rudeabort-method.md)|Anula el cálculo que este `ICorDebugEval2` está realizando actualmente.|  
  
## <a name="remarks"></a>Notas  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
