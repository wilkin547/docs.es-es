---
description: 'Más información sobre: ICorPublishProcess:: EnumAppDomains ((método)'
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
ms.openlocfilehash: c7834b23967ab467c1589ee31929bf346b4b3b8f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794616"
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
  
## <a name="see-also"></a>Vea también

- [ICorPublishProcess (Interfaz)](icorpublishprocess-interface.md)
