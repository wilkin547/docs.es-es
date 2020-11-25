---
title: ICorDebugRegisterSet (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
ms.openlocfilehash: 940810288b72be0d4dfc5366176663c22c369ebb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712384"
---
# <a name="icordebugregisterset-interface"></a>ICorDebugRegisterSet (Interfaz)

Representa el conjunto de registros disponibles en el equipo que está ejecutando código actualmente.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetRegisters (Método)](icordebugregisterset-getregisters-method.md)|Obtiene el valor de cada registro (en el equipo que está ejecutando código actualmente) especificado por la máscara de bits.|  
|[GetRegistersAvailable (Método)](icordebugregisterset-getregistersavailable-method.md)|Obtiene una máscara de bits que indica qué registros de `ICorDebugRegisterSet` están disponibles actualmente.|  
|[GetThreadContext (Método)](icordebugregisterset-getthreadcontext-method.md)|Obtiene el contexto del subproceso actual.|  
|[Método SetRegisters](icordebugregisterset-setregisters-method.md)|No se ha implementado para la versión .NET Framework 2,0.|  
|[Método SetThreadContext](icordebugregisterset-setthreadcontext-method.md)|No se ha implementado para el .NET Framework 2,0.|  
  
## <a name="remarks"></a>Comentarios  

 La `ICorDebugRegisterSet` interfaz solo admite registros de 32 bits. Use la interfaz [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) en plataformas como IA-64 que requieran registros adicionales.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [ICorDebugRegisterSet2 (Interfaz)](icordebugregisterset2-interface.md)
