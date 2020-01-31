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
ms.openlocfilehash: 795e9f4862992d95eeef98a986545cca47d828c6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784140"
---
# <a name="icordebugclass2-interface"></a>Interfaz ICorDebugClass2

Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>. Esta interfaz extiende [ICorDebugClass](icordebugclass-interface.md).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetParameterizedType (método)](icordebugclass2-getparameterizedtype-method.md)|Obtiene la declaración de tipos para esta clase.|  
|[SetJMCStatus (método)](icordebugclass2-setjmcstatus-method.md)|Para cada método de esta clase, establece un valor que indica si el método es código definido por el usuario.|  
  
## <a name="remarks"></a>Notas  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugClass (interfaz)](icordebugclass-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
