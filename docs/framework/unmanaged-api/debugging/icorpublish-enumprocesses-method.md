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
ms.openlocfilehash: 297f672097dd6561a971608f368369c623532907
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716920"
---
# <a name="icorpublishenumprocesses-method"></a>ICorPublish::EnumProcesses (Método)

Obtiene un enumerador para los procesos administrados que se ejecutan en este equipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `Type`  
 Valor de la enumeración [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) que especifica el tipo de proceso que se va a recuperar. En la versión actual, solo COR_PUB_MANAGEDONLY es válido.  
  
 `ppIEnum`  
 Puntero a la dirección de una instancia de [ICorPublishProcessEnum (](icorpublishprocessenum-interface.md) que es el enumerador de los procesos.  
  
## <a name="remarks"></a>Comentarios  

 La colección de procesos del enumerador se basa en una instantánea de los procesos que se ejecutan cuando `EnumProcesses` se llama al método. El enumerador no incluirá los procesos que finalicen antes o después de que `EnumProcesses` se llame a.  
  
 `EnumProcesses`Se puede llamar al método más de una vez en esta instancia de [ICorPublish](icorpublish-interface.md) para crear una nueva colección de procesos actualizada. Las llamadas subsiguientes del método no afectarán a las colecciones existentes `EnumProcesses` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorPublish (Interfaz)](icorpublish-interface.md)
