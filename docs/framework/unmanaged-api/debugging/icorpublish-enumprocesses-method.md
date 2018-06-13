---
title: ICorPublish::EnumProcesses (Método)
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2779138a0999e34ad6424d76ddfebbcfdf611d58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422902"
---
# <a name="icorpublishenumprocesses-method"></a>ICorPublish::EnumProcesses (Método)
Obtiene un enumerador para los procesos administrados que se ejecutan en este equipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `Type`  
 Un valor de la [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeración que especifica el tipo de proceso va a recuperar. En la versión actual, solamente es válido COR_PUB_MANAGEDONLY.  
  
 `ppIEnum`  
 Un puntero a la dirección de un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instancia que es el enumerador de los procesos.  
  
## <a name="remarks"></a>Comentarios  
 Colección del enumerador de procesos se basa en una instantánea de los procesos que se ejecutan cuando el `EnumProcesses` se llama al método. El enumerador no incluirá los procesos que finalicen antes o se inician después de `EnumProcesses` se llama.  
  
 El `EnumProcesses` método puede llamarse varias veces en el objeto [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instancia para crear una nueva colección actualizada de procesos. Las colecciones existentes no se verán afectadas por las llamadas subsiguientes de la `EnumProcesses` método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cordebug.idl, CorPub.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorPublish (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
