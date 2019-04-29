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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b0a5d80d984a3c696b178c4d8c936bd47354945
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782881"
---
# <a name="icordebugregisterset-interface"></a>ICorDebugRegisterSet (Interfaz)
Representa el conjunto de registros disponibles en el equipo que está ejecutando el código.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetRegisters (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|Obtiene el valor de cada registro (en el equipo que está ejecutando el código) especificado por la máscara de bits.|  
|[GetRegistersAvailable (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|Obtiene un poco de máscara que indica que se registra en este `ICorDebugRegisterSet` están disponibles actualmente.|  
|[GetThreadContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|Obtiene el contexto del subproceso actual.|  
|[SetRegisters (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|No se ha implementado para la versión 2.0 de .NET Framework.|  
|[SetThreadContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|No se ha implementado para .NET Framework 2.0.|  
  
## <a name="remarks"></a>Comentarios  
 El `ICorDebugRegisterSet` interfaz admite registros sólo de 32 bits. Use la [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interfaz en plataformas como IA-64 que requieran registros adicionales.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ICorDebugRegisterSet2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
