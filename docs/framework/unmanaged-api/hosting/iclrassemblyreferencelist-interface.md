---
title: ICLRAssemblyReferenceList (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
ms.openlocfilehash: a75235cd0ac0e55412f0ba58881796e3ebc801f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679246"
---
# <a name="iclrassemblyreferencelist-interface"></a>ICLRAssemblyReferenceList (Interfaz)

Administra una lista de ensamblados cargados por el Common Language Runtime (CLR) y no por el host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método IsAssemblyReferenceInList](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|Obtiene un valor que indica si el puntero proporcionado hace referencia a un ensamblado de la lista.|  
|[Método IsStringAssemblyReferenceInList](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|Obtiene un valor que indica si el nombre proporcionado coincide con el nombre de un ensamblado de la lista.|  
  
## <a name="remarks"></a>Comentarios  

 Llame al método [ICLRAssemblyIdentityManager:: getclrassemblyreferencelist (](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) para obtener un puntero a una instancia de `ICLRAssemblyReferenceList` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRAssemblyIdentityManager (Interfaz)](iclrassemblyidentitymanager-interface.md)
- [IHostAssemblyStore (Interfaz)](ihostassemblystore-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
