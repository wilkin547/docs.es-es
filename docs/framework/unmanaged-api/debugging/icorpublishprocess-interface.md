---
title: ICorPublishProcess (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08dfa3ddbfd9cffdb0cb88d0325e5703a854668a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182967"
---
# <a name="icorpublishprocess-interface"></a>ICorPublishProcess (Interfaz)
Proporciona métodos que tienen acceso a mostrar información acerca de un proceso.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EnumAppDomains](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|Obtiene un [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instancia que contiene los dominios de aplicación en el proceso que hace referencia esta `ICorPublishProcess`.|  
|[Método GetDisplayName](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|Obtiene la ruta de acceso completa del archivo ejecutable para el proceso que hace referencia esta `ICorPublishProcess`.|  
|[Método GetProcessID](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|Obtiene el identificador del sistema operativo para el proceso que hace referencia esta `ICorPublishProcess`.|  
|[Método IsManaged](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|Obtiene un valor que indica si el proceso que hace referencia esta `ICorPublishProcess` se sabe que se ejecuta código administrado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorPub.idl, CorPub.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [CorpubPublish (coclase)](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
