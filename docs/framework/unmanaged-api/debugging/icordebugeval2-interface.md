---
title: ICorDebugEval2 Interfaz1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da4364e132e2a9d578a761eea77d0dfc8d0b92aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugeval2-interface1"></a>ICorDebugEval2 Interfaz1
Extiende "ICorDebugEval" para proporcionar compatibilidad con tipos genéricos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CallParameterizedFunction (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|Configura una llamada a la especificada "ICorDebugFunction", que se puede anidar dentro de un tipo cuyo constructor toma parámetros de tipo, o puede tomar parámetros de tipo por sí misma.|  
|[CreateValueForType (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|Obtiene un puntero a un nueva "ICorDebugValue" del tipo especificado, con un valor inicial de cero o null.|  
|[NewParameterizedArray (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|Asigna una nueva matriz del tipo de elemento especificado y dimensiones.|  
|[NewParameterizedObject (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|Crea un nuevo objeto de tipo parametrizado y llama al método del objeto constructor.|  
|[NewParameterizedObjectNoConstructor (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|Crea un nuevo objeto de tipo parametrizado de la clase especificada sin intentar llamar a un método de constructor|  
|[NewStringWithLength (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|Crea una nueva cadena de la longitud especificada con el contenido especificado.|  
|[RudeAbort (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|Anula el cálculo que este `ICorDebugEval2` está realizando actualmente.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
