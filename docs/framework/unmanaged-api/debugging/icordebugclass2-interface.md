---
title: Interfaz ICorDebugClass2
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
ms.openlocfilehash: ce3f289ae914817071fad5274c45d1e5fae71a06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717986"
---
# <a name="icordebugclass2-interface"></a>Interfaz ICorDebugClass2

Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>. Esta interfaz extiende [ICorDebugClass](icordebugclass-interface.md).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetParameterizedType](icordebugclass2-getparameterizedtype-method.md)|Obtiene la declaración de tipos para esta clase.|  
|[SetJMCStatus (Método)](icordebugclass2-setjmcstatus-method.md)|Para cada método de esta clase, establece un valor que indica si el método es código definido por el usuario.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugClass](icordebugclass-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
