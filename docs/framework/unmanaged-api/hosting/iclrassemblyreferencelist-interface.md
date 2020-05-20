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
ms.openlocfilehash: f1aa40ef868bf6ff7730e01ab66a6fec58af1196
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615883"
---
# <a name="iclrassemblyreferencelist-interface"></a>ICLRAssemblyReferenceList (Interfaz)
Administra una lista de ensamblados cargados por el Common Language Runtime (CLR) y no por el host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método IsAssemblyReferenceInList](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|Obtiene un valor que indica si el puntero proporcionado hace referencia a un ensamblado de la lista.|  
|[Método IsStringAssemblyReferenceInList](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|Obtiene un valor que indica si el nombre proporcionado coincide con el nombre de un ensamblado de la lista.|  
  
## <a name="remarks"></a>Observaciones  
 Llame al método [ICLRAssemblyIdentityManager:: getclrassemblyreferencelist (](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) para obtener un puntero a una instancia de `ICLRAssemblyReferenceList` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ICLRAssemblyIdentityManager (Interfaz)](iclrassemblyidentitymanager-interface.md)
- [IHostAssemblyStore (Interfaz)](ihostassemblystore-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
