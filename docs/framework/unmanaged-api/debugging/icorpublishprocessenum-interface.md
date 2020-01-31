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
ms.openlocfilehash: 188ff8feabd704d828256a09aca20f9db2227f2c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790506"
---
# <a name="icorpublishprocessenum-interface"></a>ICorPublishProcessEnum (Interfaz)
Una subclase de la interfaz [ICorPublishEnum](icorpublishenum-interface.md) que proporciona métodos para atravesar una colección de objetos [ICorPublishProcess](icorpublishprocess-interface.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (método)](icorpublishprocessenum-next-method.md)|Obtiene el número especificado de instancias de `ICorPublishProcess` de la colección, comenzando en la posición actual.|  
  
## <a name="remarks"></a>Notas  
 La interfaz de `ICorPublishProcessEnum` implementa los métodos de la interfaz abstracta, [ICorPublishEnum](icorpublishenum-interface.md).  
  
 El método [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) crea una instancia `ICorPublishProcessEnum`. El recorrido de la colección de objetos de `ICorPublishProcess` se basa en los criterios de filtro dados en el momento en que se creó la instancia de `ICorPublishProcessEnum`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [CorpubPublish (coclase)](corpubpublish-coclass.md)
