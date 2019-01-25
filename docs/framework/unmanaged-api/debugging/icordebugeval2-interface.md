---
title: ICorDebugEval2 (Interfaz1)
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
ms.openlocfilehash: 7c50dc8e40b6565ae1bf3a5d83f4deb80d2bf0a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712988"
---
# <a name="icordebugeval2-interface1"></a>ICorDebugEval2 (Interfaz1)
Extiende "ICorDebugEval" para proporcionar compatibilidad con tipos genéricos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CallParameterizedFunction (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|Configura una llamada a la especificada "ICorDebugFunction", que se puede anidar dentro de un tipo cuyo constructor toma parámetros de tipo, o puede tomar parámetros de tipo por sí misma.|  
|[CreateValueForType (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|Obtiene un puntero a un nuevo "ICorDebugValue" del tipo especificado, con un valor inicial de cero o null.|  
|[NewParameterizedArray (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|Asigna una nueva matriz del tipo de elemento especificado y las dimensiones.|  
|[NewParameterizedObject (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|Crea una instancia de un nuevo objeto de tipo parametrizado y llama al método de constructor del objeto.|  
|[NewParameterizedObjectNoConstructor (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|Crea una instancia de un nuevo objeto de tipo parametrizado de la clase especificada sin intentar llamar a un método de constructor|  
|[NewStringWithLength (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|Crea una nueva cadena de la longitud especificada con el contenido especificado.|  
|[RudeAbort (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|Anula el cálculo que `ICorDebugEval2` está realizando actualmente.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
