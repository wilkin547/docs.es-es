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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3536184fa7798ac8eabe851221ec692c126460b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorpublishenum-interface"></a>ICorPublishEnum (Interfaz)
Actúa como la interfaz base abstracta para los enumeradores que se utilizan en la publicación de información sobre procesos y dominios de aplicación.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Clone (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|Crea una copia de esta `ICorPublishEnum` objeto.|  
|[GetCount (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|Obtiene el número de elementos de la enumeración.|  
|[Reset (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|Mueve el cursor de hasta el principio de la enumeración.|  
|[Skip (método)](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|Mueve el cursor hacia delante en la enumeración el número especificado de elementos.|  
  
## <a name="remarks"></a>Comentarios  
 Los enumeradores siguientes derivan de `ICorPublishEnum`:  
  
-   [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cordebug.idl, CorPub.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [CorpubPublish (coclase)](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
