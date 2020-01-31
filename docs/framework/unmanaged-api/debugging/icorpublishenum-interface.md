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
ms.openlocfilehash: f54bb99df60d7b3fb7bb98de75fbae210597e45c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790622"
---
# <a name="icorpublishenum-interface"></a>ICorPublishEnum (Interfaz)
Actúa como la interfaz base abstracta para los enumeradores que se usan en la publicación de información sobre los procesos y los dominios de aplicación.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Clone (método)](icorpublishenum-clone-method.md)|Crea una copia de este objeto `ICorPublishEnum`.|  
|[GetCount (método)](icorpublishenum-getcount-method.md)|Obtiene el número de elementos de la enumeración.|  
|[Reset (método)](icorpublishenum-reset-method.md)|Mueve el cursor hasta el principio de la enumeración.|  
|[Skip (método)](icorpublishenum-skip-method.md)|Mueve el cursor hacia delante en la enumeración el número de elementos especificado.|  
  
## <a name="remarks"></a>Notas  
 Los enumeradores siguientes derivan de `ICorPublishEnum`:  
  
- [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)  
  
- [ICorPublishProcessEnum](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CorpubPublish (coclase)](corpubpublish-coclass.md)
- [Interfaces de depuración](debugging-interfaces.md)
