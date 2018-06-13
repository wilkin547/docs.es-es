---
title: ICorDebugExceptionObjectValue (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6805b7b49f76b80161aef5051fe3c284192f582
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413779"
---
# <a name="icordebugexceptionobjectvalue-interface"></a>ICorDebugExceptionObjectValue (Interfaz)
Extiende la interfaz "ICorDebugObjectValue" para proporcionar información de seguimiento de pila de un objeto de excepción administrada.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumerateExceptionCallStack (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|Obtiene un enumerador para la pila de llamadas que se incrustan en un objeto de excepción.|  
  
## <a name="remarks"></a>Comentarios  
 La llamada a `QueryInterface` se realizará correctamente para objetos administrados que se derivan de <xref:System.Exception?displayProperty=nameWithType>.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 
