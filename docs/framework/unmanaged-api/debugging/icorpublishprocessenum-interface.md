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
ms.openlocfilehash: 657d2d638a419ba88d4cf7152f4505de1bd23706
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421077"
---
# <a name="icorpublishprocessenum-interface"></a>ICorPublishProcessEnum (Interfaz)
Una subclase de la interfaz [ICorPublishEnum](icorpublishenum-interface.md) que proporciona métodos para atravesar una colección de objetos [ICorPublishProcess](icorpublishprocess-interface.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (Método)](icorpublishprocessenum-next-method.md)|Obtiene el número especificado de `ICorPublishProcess` instancias de la colección, comenzando en la posición actual.|  
  
## <a name="remarks"></a>Observaciones  
 La `ICorPublishProcessEnum` interfaz implementa los métodos de la interfaz abstracta, [ICorPublishEnum](icorpublishenum-interface.md).  
  
 `ICorPublishProcessEnum`El método [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) crea una instancia. El recorrido de la colección de `ICorPublishProcess` objetos se basa en los criterios de filtro dados en el momento en que `ICorPublishProcessEnum` se creó la instancia.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Interfaces para depuración](debugging-interfaces.md)
- [CorpubPublish (coclase)](corpubpublish-coclass.md)
