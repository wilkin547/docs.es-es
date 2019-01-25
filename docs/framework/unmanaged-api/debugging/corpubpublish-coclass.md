---
title: CorpubPublish (coclase)
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a0d796b9c507665ff3ba67153df4691f078e5c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543846"
---
# <a name="corpubpublish-coclass"></a>CorpubPublish (coclase)
Proporciona interfaces para publicar información acerca de procesos y dominios de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a>Interfaces  
  
|Interfaz|Descripción|  
|---------------|-----------------|  
|[ICorPublish (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|Proporciona métodos para publicar información acerca de los procesos y los dominios de aplicación en esos procesos.|  
|[ICorPublishAppDomain (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|Representa y proporciona información sobre un dominio de aplicación en un proceso.|  
|[ICorPublishAppDomainEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|Proporciona métodos que atraviesan una colección de dominios de aplicación que existen actualmente dentro de un proceso.|  
|[ICorPublishProcess (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|Representa un proceso que se ejecuta en un equipo.|  
|[ICorPublishProcessEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|Proporciona métodos que atraviesan una colección de procesos que se ejecutan en un equipo.|  
  
## <a name="remarks"></a>Comentarios  
 Un escenario de publicación típico implica un programador que desea depurar código administrado que se ejecuta en un equipo dentro de un dominio de aplicación. El entorno de hospedaje puede ejecutarse más de un dominio de aplicación dentro de un proceso. El desarrollador le gustaría usar una interfaz gráfica de usuario u otros medios para enumerar todos los procesos que se ejecutan en el equipo y elegir un proceso específico. La lista debe incluir todos los dominios de aplicación dentro de los procesos que ejecutan código administrado. El desarrollador puede identificar el dominio de aplicación concreto y asociar a un depurador a ese dominio.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorPub.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
