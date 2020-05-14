---
title: ICorPublishAppDomainEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
ms.openlocfilehash: a48e20413f466e25a9145e9dbf1ba93d90155770
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397041"
---
# <a name="icorpublishappdomainenum-interface"></a>ICorPublishAppDomainEnum (Interfaz)
Una subclase de la interfaz [ICorPublishEnum](icorpublishenum-interface.md) que proporciona métodos para atravesar una colección de objetos [ICorPublishAppDomain](icorpublishappdomain-interface.md) que existen actualmente dentro de un proceso.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (Método)](icorpublishappdomainenum-next-method.md)|Obtiene el número especificado de `ICorPublishAppDomain` instancias de la colección, comenzando en la posición actual.|  
  
## <a name="remarks"></a>Comentarios  
 La `ICorPublishAppDomainEnum` interfaz implementa los métodos de la interfaz abstracta, [ICorPublishEnum](icorpublishenum-interface.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
- [CorpubPublish (coclase)](corpubpublish-coclass.md)
