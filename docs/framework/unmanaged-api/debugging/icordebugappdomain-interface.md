---
title: ICorDebugAppDomain Interfaz1
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
ms.openlocfilehash: 84a11b6264ac0e241c1975eea5626edbdddce206
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugappdomain-interface1"></a>ICorDebugAppDomain Interfaz1
Proporciona métodos para depurar dominios de aplicación. Esta interfaz es una subclase de ICorDebugController.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Attach (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|Asocia al depurador al dominio de aplicación.|  
|[EnumerateAssemblies (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|Obtiene un enumerador para los ensamblados en el dominio de aplicación.|  
|[EnumerateBreakpoints (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|Obtiene un enumerador para todos los puntos de interrupción activos en el dominio de aplicación.|  
|[EnumerateSteppers (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|Obtiene un enumerador para todos los steppers activos en el dominio de aplicación.|  
|[GetId (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|Obtiene el identificador único del dominio de aplicación.|  
|[GetModuleFromMetaDataInterface (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|Obtiene el objeto ICorDebugModule con la interfaz de metadatos especificada.|  
|[GetName (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|Obtiene el nombre del dominio de aplicación.|  
|[GetObject (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|Obtiene un puntero de interfaz al dominio de aplicación de common language runtime (CLR).|  
|[GetProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|Obtiene el proceso que contiene el dominio de aplicación.|  
|[IsAttached (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|Determina si el depurador se adjunta al dominio de aplicación.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
