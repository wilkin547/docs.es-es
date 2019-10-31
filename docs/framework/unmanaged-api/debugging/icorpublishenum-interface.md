---
title: ICorPublishEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
ms.openlocfilehash: 7d083655326333f18ee98f8e84fff2ed182dde6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103464"
---
# <a name="icorpublishenum-interface"></a>ICorPublishEnum (Interfaz)
Actúa como la interfaz base abstracta para los enumeradores que se usan en la publicación de información sobre los procesos y los dominios de aplicación.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Clone (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|Crea una copia de este objeto `ICorPublishEnum`.|  
|[GetCount (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|Obtiene el número de elementos de la enumeración.|  
|[Reset (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|Mueve el cursor hasta el principio de la enumeración.|  
|[Skip (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|Mueve el cursor hacia delante en la enumeración el número de elementos especificado.|  
  
## <a name="remarks"></a>Comentarios  
 Los enumeradores siguientes derivan de `ICorPublishEnum`:  
  
- [ICorPublishAppDomainEnum (](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
- [ICorPublishProcessEnum (](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CorpubPublish (coclase)](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
