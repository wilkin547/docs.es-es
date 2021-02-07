---
description: 'Más información acerca de: interfaz ICorDebugEval2'
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
ms.openlocfilehash: 2c279335bdd30b8dc2698f348d9537443b236a45
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693764"
---
# <a name="icordebugeval2-interface"></a>Interfaz ICorDebugEval2

Extiende "ICorDebugEval" para proporcionar compatibilidad con los tipos genéricos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md)|Configura una llamada a la instrucción "ICorDebugFunction" especificada, que puede estar anidada dentro de un tipo cuyo constructor toma parámetros de tipo, o bien puede tomar parámetros de tipo.|  
|[Método CreateValueForType](icordebugeval2-createvaluefortype-method.md)|Obtiene un puntero a una nueva expresión "ICorDebugValue" del tipo especificado, con un valor inicial de null o cero.|  
|[Método NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md)|Asigna una nueva matriz del tipo de elemento y las dimensiones especificadas.|  
|[Método NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md)|Crea una instancia de un nuevo objeto de tipo parametrizado y llama al método de constructor del objeto.|  
|[Método NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|Crea una instancia de un nuevo objeto de tipo parametrizado de la clase especificada sin intentar llamar a un método de constructor.|  
|[Método NewStringWithLength](icordebugeval2-newstringwithlength-method.md)|Crea una nueva cadena de la longitud especificada con el contenido especificado.|  
|[RudeAbort (Método)](icordebugeval2-rudeabort-method.md)|Anula el cálculo que `ICorDebugEval2` está realizando actualmente.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
