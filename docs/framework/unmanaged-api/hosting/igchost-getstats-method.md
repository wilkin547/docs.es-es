---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14751b41809eeda5e6bd990fae368879d0f30492
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927255"
---
# <a name="igchostgetstats-method"></a>IGCHost::GetStats (Método)
Obtiene las estadísticas para el estado actual del sistema de recopilación de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pStats`  
 [in, out] Un puntero a un [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) estructura que contiene las estadísticas para el estado actual del sistema de recopilación de elementos no utilizados.  
  
## <a name="remarks"></a>Comentarios  
 Las estadísticas se pueden usar un sistema de asignación inteligente para el sistema de recopilación de elementos no utilizados que funcione. Por ejemplo, puede determinar el sistema de asignación después de revisar las estadísticas, lo que necesita para agregar más memoria o forzar una recolección.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: GCHost.idl, GCHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IGCHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
