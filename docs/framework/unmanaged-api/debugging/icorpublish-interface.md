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
ms.openlocfilehash: 3ff4efe8b3e2932da7f65246bf4ad614a4dd86cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694417"
---
# <a name="icorpublish-interface"></a>ICorPublish (Interfaz)

Actúa como la interfaz general para publicar información sobre procesos e información sobre los dominios de aplicación en esos procesos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EnumProcesses](icorpublish-enumprocesses-method.md)|Obtiene una instancia de [ICorPublishProcessEnum (](icorpublishprocessenum-interface.md) que contiene los procesos administrados que se ejecutan en este equipo.|  
|[Método GetProcess](icorpublish-getprocess-method.md)|Obtiene una instancia de [ICorPublishProcess](icorpublishprocess-interface.md) que representa el proceso con el identificador especificado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [CorpubPublish (coclase)](corpubpublish-coclass.md)
