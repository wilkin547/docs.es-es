---
title: Interfaz ICorDebugAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
ms.openlocfilehash: 821eae8ea5b4147408e9fe60d1e5b70c7936959e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696250"
---
# <a name="icordebugassembly-interface"></a>Interfaz ICorDebugAssembly

Representa un ensamblado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EnumerateModules](icordebugassembly-enumeratemodules-method.md)|Obtiene un enumerador para los módulos incluidos en el ensamblado.|  
|[Método GetAppDomain](icordebugassembly-getappdomain-method.md)|Obtiene un puntero de interfaz al dominio de aplicación que contiene esta `ICorDebugAssembly` instancia.|  
|[Método GetCodeBase](icordebugassembly-getcodebase-method.md)|No se implementa en la versión actual del .NET Framework.|  
|[GetName (Método)](icordebugassembly-getname-method.md)|Obtiene el nombre del ensamblado.|  
|[Método GetProcess](icordebugassembly-getprocess-method.md)|Obtiene la instancia de ICorDebugProcess en la que se ejecuta el ensamblado.|  
  
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
