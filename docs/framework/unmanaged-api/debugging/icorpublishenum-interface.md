---
title: ICorPublishEnum (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishEnum
helpviewer_keywords: ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7034945824e439b42134f8ea3c13bfaf73dbb649
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [CorpubPublish (Coclase)](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
