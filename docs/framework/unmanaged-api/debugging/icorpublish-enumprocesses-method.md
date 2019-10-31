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
ms.openlocfilehash: 5f0dd814ad5adfa1b0dd7199530a3f993634a548
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121798"
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
 Valor de la enumeración [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) que especifica el tipo de proceso que se va a recuperar. En la versión actual, solo COR_PUB_MANAGEDONLY es válido.  
  
 `ppIEnum`  
 Puntero a la dirección de una instancia de [ICorPublishProcessEnum (](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) que es el enumerador de los procesos.  
  
## <a name="remarks"></a>Comentarios  
 La colección de procesos del enumerador se basa en una instantánea de los procesos que se están ejecutando cuando se llama al método `EnumProcesses`. El enumerador no incluirá ningún proceso que finalice antes o iniciar después de llamar a `EnumProcesses`.  
  
 Se puede llamar al método `EnumProcesses` más de una vez en esta instancia de [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) para crear una nueva colección de procesos actualizada. Las llamadas subsiguientes del método `EnumProcesses` no afectarán a las colecciones existentes.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorPublish (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
