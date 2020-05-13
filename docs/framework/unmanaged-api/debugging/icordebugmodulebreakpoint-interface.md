---
title: Interfaz ICorDebugModuleBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint
helpviewer_keywords:
- ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type:
- apiref
ms.openlocfilehash: 7026d135b02563b6c718be4096d2c5cad9d33cec
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212287"
---
# <a name="icordebugmodulebreakpoint-interface"></a>Interfaz ICorDebugModuleBreakpoint

Proporciona acceso a módulos específicos. Esta interfaz es una subclase de la interfaz ICorDebugBreakpoint.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetModule (Método)](icordebugmodulebreakpoint-getmodule-method.md)|Obtiene un puntero de interfaz a una ICorDebugModule que hace referencia al módulo donde se establece este punto de interrupción.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
