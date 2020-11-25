---
title: Interfaz ICorDebugFunction2
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
ms.openlocfilehash: d9e84a70d72db1338c80140ce3350774bfae4bca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726280"
---
# <a name="icordebugfunction2-interface"></a>Interfaz ICorDebugFunction2

Extiende lógicamente la interfaz ICorDebugFunction para proporcionar compatibilidad con Solo mi código depuración paso a paso, que omite el código que no es de usuario.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EnumerateNativeCode](icordebugfunction2-enumeratenativecode-method.md)|(Aún no implementado). Obtiene un puntero de interfaz a un ICorDebugCodeEnum (que contiene las instrucciones de código nativo en la función a la que hace referencia este objeto ICorDebugFunction2.|  
|[Método GetJMCStatus](icordebugfunction2-getjmcstatus-method.md)|Obtiene un valor que indica si esta función está marcada como código de usuario.|  
|[GetVersionNumber (Método)](icordebugfunction2-getversionnumber-method.md)|Obtiene la versión de edición y continuación de esta función.|  
|[SetJMCStatus (Método)](icordebugfunction2-setjmcstatus-method.md)|Marca esta función para Solo mi código la ejecución paso a paso.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
