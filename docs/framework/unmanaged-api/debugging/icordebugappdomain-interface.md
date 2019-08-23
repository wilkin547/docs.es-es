---
title: Interfaz ICorDebugAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12753ab65f9339e8f6c3049bb72755e87464eb1a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963107"
---
# <a name="icordebugappdomain-interface"></a>Interfaz ICorDebugAppDomain

Proporciona métodos para depurar dominios de aplicación. Esta interfaz es una subclase de ICorDebugController.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|[Attach (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|Asocia el depurador al dominio de aplicación.|  
|[EnumerateAssemblies (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|Obtiene un enumerador para los ensamblados en el dominio de aplicación.|  
|[EnumerateBreakpoints (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|Obtiene un enumerador para todos los puntos de interrupción activos en el dominio de aplicación.|  
|[EnumerateSteppers (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|Obtiene un enumerador para todos los steppers activos en el dominio de aplicación.|  
|[GetId (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|Obtiene el identificador único del dominio de aplicación.|  
|[GetModuleFromMetaDataInterface (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|Obtiene el objeto ICorDebugModule con la interfaz de metadatos especificada.|  
|[GetName (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|Obtiene el nombre del dominio de aplicación.|  
|[GetObject (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|Obtiene un puntero de interfaz al dominio de aplicación de Common Language Runtime (CLR).|  
|[GetProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|Obtiene el proceso que contiene el dominio de aplicación.|  
|[IsAttached (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|Determina si el depurador está asociado al dominio de aplicación.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cordebug. idl, Cordebug. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
