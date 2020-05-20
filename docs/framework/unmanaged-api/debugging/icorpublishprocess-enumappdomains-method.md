---
title: ICorPublishProcess::EnumAppDomains (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
ms.openlocfilehash: 0c3b5da52b78150198fa9f910bf01b4657e4eba8
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421168"
---
# <a name="icorpublishprocessenumappdomains-method"></a>ICorPublishProcess::EnumAppDomains (Método)
Obtiene un enumerador para los dominios de aplicación en el proceso al que hace referencia esta [ICorPublishProcess](icorpublishprocess-interface.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppEnum`  
 enuncia Un puntero a la dirección de una instancia de [ICorPublishAppDomainEnum (](icorpublishappdomainenum-interface.md) que permite la iteración a través de la colección de dominios de aplicación en este proceso.  
  
## <a name="remarks"></a>Observaciones  
 La lista de dominios de aplicación se basa en una instantánea de los dominios de aplicación que existen cuando `EnumAppDomains` se llama al método. Este método se puede llamar más de una vez para crear una nueva lista actualizada. Las llamadas subsiguientes de este método no afectarán a las listas existentes.  
  
 Si se ha finalizado el proceso, `EnumAppDomains` se producirá un error HRESULT con el valor CORDBG_E_PROCESS_TERMINATED.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ICorPublishProcess (Interfaz)](icorpublishprocess-interface.md)
