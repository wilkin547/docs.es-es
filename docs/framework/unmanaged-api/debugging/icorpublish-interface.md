---
title: ICorPublish (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65daa8d783210426136860d95dd5782e21de33a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorpublish-interface"></a>ICorPublish (Interfaz)
Actúa como interfaz general para publicar información acerca de los procesos e información sobre los dominios de aplicación en esos procesos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumProcesses (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|Obtiene un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instancia que contiene los procesos administrados que se ejecutan en este equipo.|  
|[GetProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|Obtiene un [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instancia que representa el proceso con el identificador especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cordebug.idl, CorPub.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [CorpubPublish (coclase)](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
