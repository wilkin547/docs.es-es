---
description: 'Más información acerca de: ICorDebugAppDomain (interfaz)'
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
ms.openlocfilehash: 5f1ac20a7376a741da2e34de74c810c0f45e8293
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754205"
---
# <a name="icordebugappdomain-interface"></a>Interfaz ICorDebugAppDomain

Proporciona métodos para depurar dominios de aplicación. Esta interfaz es una subclase de ICorDebugController.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Attach](icordebugappdomain-attach-method.md)|Asocia el depurador al dominio de aplicación.|  
|[Método EnumerateAssemblies](icordebugappdomain-enumerateassemblies-method.md)|Obtiene un enumerador para los ensamblados en el dominio de aplicación.|  
|[Método EnumerateBreakpoints](icordebugappdomain-enumeratebreakpoints-method.md)|Obtiene un enumerador para todos los puntos de interrupción activos en el dominio de aplicación.|  
|[Método EnumerateSteppers](icordebugappdomain-enumeratesteppers-method.md)|Obtiene un enumerador para todos los steppers activos en el dominio de aplicación.|  
|[GetId (método)](icordebugappdomain-getid-method.md)|Obtiene el identificador único del dominio de aplicación.|  
|[Método GetModuleFromMetaDataInterface](icordebugappdomain-getmodulefrommetadatainterface-method.md)|Obtiene el objeto ICorDebugModule con la interfaz de metadatos especificada.|  
|[Método GetName](icordebugappdomain-getname-method.md)|Obtiene el nombre del dominio de aplicación.|  
|[GetObject (Método)](icordebugappdomain-getobject-method.md)|Obtiene un puntero de interfaz al dominio de aplicación de Common Language Runtime (CLR).|  
|[Método GetProcess](icordebugappdomain-getprocess-method.md)|Obtiene el proceso que contiene el dominio de aplicación.|  
|[Método IsAttached](icordebugappdomain-isattached-method.md)|Determina si el depurador está asociado al dominio de aplicación.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
