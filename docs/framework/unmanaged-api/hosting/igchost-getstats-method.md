---
description: 'Más información sobre: IGCHost:: Getstats ((método)'
title: IGCHost::GetStats (Método)
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
ms.openlocfilehash: 564224d01e23c8ac1fe81025ee87dabc41ed5166
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709700"
---
# <a name="igchostgetstats-method"></a>IGCHost::GetStats (Método)

Obtiene las estadísticas para el estado actual del sistema de recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pStats`  
 [in, out] Puntero a una estructura de [COR_GC_STATS](cor-gc-stats-structure.md) que contiene las estadísticas para el estado actual del sistema de recolección de elementos no utilizados.  
  
## <a name="remarks"></a>Observaciones  

 Las estadísticas se pueden usar en un sistema de asignación inteligente para ayudar al funcionamiento del sistema de recolección de elementos no utilizados. Por ejemplo, el sistema de asignación puede determinar, después de revisar las estadísticas, que necesita agregar más memoria o forzar una colección.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** GCHost. idl, GCHost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IGCHost (Interfaz)](igchost-interface.md)
