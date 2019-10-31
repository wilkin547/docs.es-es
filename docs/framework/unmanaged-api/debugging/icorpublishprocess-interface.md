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
ms.openlocfilehash: 04f6a088c5bbe96e3909ba600aa8ffab937abe2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140403"
---
# <a name="icorpublishprocess-interface"></a>ICorPublishProcess (Interfaz)
Proporciona métodos que tienen acceso a la información que se va a mostrar sobre un proceso.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumAppDomains (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|Obtiene una instancia de [ICorPublishAppDomainEnum (](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) que contiene los dominios de aplicación en el proceso al que hace referencia este `ICorPublishProcess`.|  
|[GetDisplayName (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|Obtiene la ruta de acceso completa del archivo ejecutable para el proceso al que hace referencia este `ICorPublishProcess`.|  
|[GetProcessID (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|Obtiene el identificador del sistema operativo para el proceso al que hace referencia este `ICorPublishProcess`.|  
|[IsManaged (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|Obtiene un valor que indica si se sabe que el proceso al que hace referencia esta `ICorPublishProcess` está ejecutando código administrado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [CorpubPublish (coclase)](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
