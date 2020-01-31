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
ms.openlocfilehash: 61cac0922423acabef3d47618d98ddf082d071da
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790678"
---
# <a name="icorpublishappdomainenum-interface"></a>ICorPublishAppDomainEnum (Interfaz)
Una subclase de la interfaz [ICorPublishEnum](icorpublishenum-interface.md) que proporciona métodos para atravesar una colección de objetos [ICorPublishAppDomain](icorpublishappdomain-interface.md) que existen actualmente dentro de un proceso.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (método)](icorpublishappdomainenum-next-method.md)|Obtiene el número especificado de instancias de `ICorPublishAppDomain` de la colección, comenzando en la posición actual.|  
  
## <a name="remarks"></a>Notas  
 La interfaz de `ICorPublishAppDomainEnum` implementa los métodos de la interfaz abstracta, [ICorPublishEnum](icorpublishenum-interface.md).  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [CorpubPublish (coclase)](corpubpublish-coclass.md)
