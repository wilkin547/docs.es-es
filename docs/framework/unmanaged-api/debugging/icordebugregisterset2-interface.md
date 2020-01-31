---
title: ICorDebugRegisterSet2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
ms.openlocfilehash: 161358fab9a4601e7b718321273d493bd84a3228
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792012"
---
# <a name="icordebugregisterset2-interface"></a>ICorDebugRegisterSet2 (Interfaz)
Extiende las capacidades de la interfaz [ICorDebugRegisterSet](icordebugregisterset-interface.md) para plataformas de hardware que tienen más de 64 registros.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetRegisters (método)](icordebugregisterset2-getregisters-method.md)|Obtiene el valor de cada registro (en el equipo que está ejecutando código actualmente) especificado por la máscara de bits.|  
|[GetRegistersAvailable (método)](icordebugregisterset2-getregistersavailable-method.md)|Obtiene una matriz de bytes que proporciona un mapa de bits de los registros disponibles.|  
|[SetRegisters (método)](icordebugregisterset2-setregisters-method.md)|No se implementa en la versión .NET Framework 2,0.|  
  
## <a name="remarks"></a>Notas  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [ICorDebugRegisterSet (interfaz)](icordebugregisterset-interface.md)
