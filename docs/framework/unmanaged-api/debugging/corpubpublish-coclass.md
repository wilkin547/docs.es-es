---
description: 'Más información acerca de: coclase Corpubpublish ('
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
ms.openlocfilehash: fdf4be6ff2d20391e989998cd0045ed27d602561
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661706"
---
# <a name="corpubpublish-coclass"></a>CorpubPublish (coclase)

Proporciona interfaces para publicar información acerca de procesos y dominios de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|[ICorPublish (Interfaz)](icorpublish-interface.md)|Proporciona métodos para publicar información sobre los procesos y los dominios de aplicación en esos procesos.|  
|[ICorPublishAppDomain (Interfaz)](icorpublishappdomain-interface.md)|Representa y proporciona información sobre un dominio de aplicación en un proceso.|  
|[ICorPublishAppDomainEnum (Interfaz)](icorpublishappdomainenum-interface.md)|Proporciona métodos que atraviesan una colección de dominios de aplicación que existen actualmente dentro de un proceso.|  
|[ICorPublishProcess (Interfaz)](icorpublishprocess-interface.md)|Representa un proceso que se está ejecutando en un equipo.|  
|[ICorPublishProcessEnum (Interfaz)](icorpublishprocessenum-interface.md)|Proporciona métodos que atraviesan una colección de procesos que se ejecutan en un equipo.|  
  
## <a name="remarks"></a>Observaciones  

 Un escenario de publicación típico implica a un desarrollador que desea depurar el código administrado que se ejecuta en un equipo dentro de un dominio de aplicación. Es posible que el entorno de hospedaje ejecute más de un dominio de aplicación dentro de un proceso. El desarrollador desea usar una interfaz gráfica de usuario u otros medios para enumerar todos los procesos que se ejecutan en el equipo y elegir un proceso específico. La lista debe incluir todos los dominios de aplicación dentro de los procesos que ejecutan código administrado. A continuación, el desarrollador puede identificar el dominio de aplicación específico y asociar un depurador a ese dominio.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Depuración](index.md)
