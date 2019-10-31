---
title: ICorPublishProcessEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: 3a7267548a957d403cfe02aa3d800a410c14b82a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103416"
---
# <a name="icorpublishprocessenum-interface"></a>ICorPublishProcessEnum (Interfaz)
Una subclase de la interfaz [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) que proporciona métodos para atravesar una colección de objetos [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|Obtiene el número especificado de instancias de `ICorPublishProcess` de la colección, comenzando en la posición actual.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz de `ICorPublishProcessEnum` implementa los métodos de la interfaz abstracta, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).  
  
 El método [ICorPublish:: EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) crea una instancia `ICorPublishProcessEnum`. El recorrido de la colección de objetos de `ICorPublishProcess` se basa en los criterios de filtro dados en el momento en que se creó la instancia de `ICorPublishProcessEnum`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [CorpubPublish (coclase)](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
